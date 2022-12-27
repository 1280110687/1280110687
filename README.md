- 👋 Hi, I’m @1280110687
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
1280110687/1280110687 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

/**
 * 从url中获取参数
 * @param {Array} keyArr // url参数
 * @returns
 */
export const GetRequest = (name) => {
  const reg = new RegExp(name + '=([^&]*)(&|$)', 'i')
  const r = window.location.href.substring(1).match(reg)
  if (r != null) {
    sessionStorage.setItem(name, decodeURIComponent(r[1]))
    return decodeURIComponent(r[1])
  }
  return null
}
使用：

const keyArr = ['reg']
keyArr.forEach((item) => {
  GetRequest(`${item}`)
})
or
GetRequest("reg")
