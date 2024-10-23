# Framer Full screen 사용법

1. Code Override의 Edit Code를 눌러 코드 편집 모드로 들어갑니다.


<img src="https://github.com/pjhppo/FramerTest/blob/main/Images/Guide.png" alt="가이드 이미지1" width="262" height="182">

2. 코드 편집 모드에서 가장 하단에 다음 코드를 붙여넣기 합니다.

```export function asPWA(Component): ComponentType {
    return (props) => {
        // 테마 색상 설정
        const metaThemeColor = document.createElement("meta")
        metaThemeColor.setAttribute("name", "theme-color")
        metaThemeColor.setAttribute("content", "#ffffff")
        document.head.appendChild(metaThemeColor)

        // iOS 상태바 색상 설정
        const metaAppleStatusBar = document.createElement("meta")
        metaAppleStatusBar.setAttribute(
            "name",
            "apple-mobile-web-app-status-bar-style"
        )
        metaAppleStatusBar.setAttribute("content", "black-translucent")
        document.head.appendChild(metaAppleStatusBar)

        // 홈화면 아이콘 설정
        const appleIcon = document.createElement("link")
        appleIcon.setAttribute("rel", "apple-touch-icon")
        appleIcon.setAttribute("sizes", "144x144")
        appleIcon.setAttribute(
            "href",
            "https://framerusercontent.com/images/l8xYBNx4GH5B0i987yubofZUKJ4.png"
        )
        document.head.appendChild(appleIcon)

        // manifest 설정
        const link = document.createElement("link")
        link.setAttribute("rel", "manifest")
        link.setAttribute(
            "href",
            "https://raw.githubusercontent.com/pjhppo/FramerTest/refs/heads/main/Scripts/Framerapp.webmanifest"
        )
        document.head.appendChild(link)

        return (
            <Component
                {...props}
                style={{ ...props.style, touchAction: "none" }}
            />
        )
    }
}```
