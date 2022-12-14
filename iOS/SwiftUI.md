# Tuist-Template (iOS - SwiftUI)
### Setting
Tuist -> ProjectDescriptionHelpers -> Environment.swift
로 가셔서 
```swift
import ProjectDescription

public enum Environment {
    public static let appName = \(앱 이름)
    public static let targetName = \(타겟 이름)
    public static let targetTestName = "\(targetName)Tests"
    public static let organizationName = \(사용자 이름)
    public static let deploymentTarget: DeploymentTarget = .iOS(targetVersion: "14.0", devices: [.iphone, .ipad])
    public static let platform = Platform.iOS
    public static let baseSetting: SettingsDictionary = SettingsDictionary()
}
```
& 

Tuist -> ProjectDescriptionHelpers -> CodeSign.swift 이동
```swift
import ProjectDescription

public extension SettingsDictionary {
    static let codeSign = SettingsDictionary()
        .codeSignIdentityAppleDevelopment()
        .automaticCodeSigning(devTeam: " 사용자의 Apple developer ID Code")
}
```

이런식으로 바꿔주시면 됩니다.

### Make File 사용법
- make generate
    - tuist fetch 이후 tuist generate 함
- make clean
    - **/*.xcodeproj 과 *.xcworkspace 모두 삭제
- make reset
    - tuist clean 후 **/*.xcodeproj 과 *.xcworkspace 모두 삭제
- make project
    - 새로운 Project 생성 
    - make project를 실행한 후 새로운 Project 세팅

### Graph

<img src = "https://github.com/Tuist-Template/GuideLine/blob/main/iOS/Image/SwiftUI/graph.png?raw=true">
