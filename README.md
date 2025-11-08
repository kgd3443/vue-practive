# what is changed?


## example1
![1](images/1.png)
![2](images/2.png)
![3](images/3.png)
```

1. data(){ return { message } } -> const message = ref('Vue!') 등, 선언이 짧아짐
2. computed를 뒤로 분리
```

## example2
![4](images/4.png)
```

1. isVisible, items, count를 ref로 전환
```

## example3
![5](images/5.png)
```

props와 emit의 사용방법 변경
1. props: ['message'] 
-> const props = defineProps({ message: { type: String, required: true } })

2. $emit('custom-event', payload) 
-> const emit = defineEmits(['custom-event']) 선언 후 emit('custom-event', payload)

자식 등록 방식, 상태/메서드 변경
1. components: { ChildComponent }
-> <script setup>에서 import ChildComponent from './ChildComponent.vue'

2. data(){ return { parentMessage: '...' } }, methods:{ handleEvent(){} }
-> const parentMessage = ref('...'), function handleEvent(...) { ... }

```

## example4
![6](images/6.png)

## example5
![7,8,9](images/7,8,9.png)
```
1. beforeDestroy → beforeUnmount
2. defineOptions() 대신 보조 <script>의 export default { name: ... }
3. title prop → initialTitle로 변경
4. 내부에 const title = ref(props.initialTitle)

```

## example6
![10](images/10.png)
![11](images/11.png)
![12](images/12.png)
```

1. <script setup> 도입
2. ref 타입에 TS 제네릭 사용: ref<HTMLInputElement | null>(null)
```

# vue-demo

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
