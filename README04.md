# react에서는 이 데이터를 변할수 있는 값이며 값이 변할때마다 UI를 변경해 달라고 (화면을 다시 그려달라) 알려야 한다. 그럴때 사용하는것이 useState()이다.

```
const [num, setNum] = useState(0)
이 데이터를 변할수 있는 값 ==> num
num을 변하게 하는 함수 ==> setNum --> 함수를 이용하여 num을 변경한다
useState(0)의 0은 num의 초기값
```


# 부분적으로 값 받기
![image](https://github.com/leesh0787/react/assets/131154479/0994b688-99e0-4b63-9a14-1748e64f690e)

```
// 폴더 src2 참조

import React from 'react'

const Profile = (props) => {
  // || --> a || b 둘중에 하나라도 true이면 true
  // && --> a && b 둘 다 true 이어야 true

  console.log(props)

  // const img = props.img
  // const name = props.name
  // const title = props.title

  // 구조분해 destructure
  const {img,name,title,isNew}= props
  return (
    <div className='profile'>
        <img src={img} alt="avatar"/>
        {/* {props.isNew?<span className='new'>신입</span>:""} */}
        {isNew&&<span className='new'>신입</span>}
        <h2>{name}</h2>
        <p>{title}</p>
    </div>
  )
}

export default Profile
```
