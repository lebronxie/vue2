## vue2 
   renderWatcher监听的  expOrFn: string | Function, 为 updateComponent
        updateComponent = () => {
      vm._update(vm._render(), hydrating)
    }
挂载 和 更新 函数 
new Watcher(vm, updateComponent, noop, {
    before () {
      if (vm._isMounted && !vm._isDestroyed) {
        callHook(vm, 'beforeUpdate')
      }
    }
  }, true /* isRenderWatcher */)

执行 getter  vm._update(vm._render(), hydrating)

vm._render()  执行编译后的render函数 生成vNode
vm._update(vNode) 挂在vNode到真实dom上


_init 扩展vue实例 vm上的属性
    mergeOptions
    initLifecycle(vm)
    initEvents(vm)
    initRender(vm)
    callHook(vm, 'beforeCreate')
    initInjections(vm) // resolve injections before data/props
    initState(vm)
    initProvide(vm) // resolve provide after data/props
    callHook(vm, 'created')
    

$mount
  compiler生成render函数 _c _v    
      生成AST 转化AST为JSAST 处理AST为render函数
  执行render函数 时 建立响应式  依赖收集   同时生产vNode
  _update(vNode) patch vNode 生成真实的dom  
