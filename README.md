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
}
```

3. 이제 프레이머 프로젝트 파일을 저장하고 업데이트 또는 퍼블리시를 합니다.

4. 모바일에서 웹링크를 사파리로 열고, 하단 내보내기 버튼 > 홈 화면에 추가 버튼을 누릅니다.

5. 홈화면에 추가된 앱 아이콘을 누르면 프레이머 페이지가 전체 화면을 변경되는것을 볼수 있습니다.


### 추가사항

#### status bar 칼라 변경 법
1. 상단의 코드에서 metaThemeColor.setAttribute("content", "#ffffff") 부분의 칼라를 변경합니다. 
2. metaAppleStatusBar.setAttribute("content", "black-translucent") 부분을 metaAppleStatusBar.setAttribute("content", "default")로 변경합니다.
