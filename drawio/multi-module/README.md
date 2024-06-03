# What's Your Plan Multi Module 설계

<img width="800" src="https://raw.githubusercontent.com/What-s-Your-Plan/repository-rule/main/image/logo.png" alt="logo" />

<div align="center">

![drawio](https://img.shields.io/badge/drawio-orange)

</div>

현재 프로젝트는 **단일 모듈**로 되어 있으며 3 Layer Architecture 로 이루어져 있습니다.

<img src="https://private-user-images.githubusercontent.com/74192619/336103354-4b998dd2-4745-4768-a914-fedd37074c33.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTc0MjQwMTcsIm5iZiI6MTcxNzQyMzcxNywicGF0aCI6Ii83NDE5MjYxOS8zMzYxMDMzNTQtNGI5OThkZDItNDc0NS00NzY4LWE5MTQtZmVkZDM3MDc0YzMzLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MDMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjAzVDE0MDgzN1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU4MjBkY2RkNjljMjhiNjRkYzlkODUzMzFiOGM5NGI5OTU3ZWQwYTI4NjZiZmY5NWVmOGMyZWQ0MWFmMGZmZjYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.ZFMb1c3dQRoiRwtiIkI-1av6Mrd7ojI-MQH2afmeZ7o" width="800" />

현재는 작은 프로젝트이지만 계속 확장을 하게 된다면 코드의 복잡성은 올라가게될 것 이고 확장성이 떨어질 것 입니다.
또한 레이어로 분리된 관심사 외에 다른 관심사가 발견된 경우, 패키지 분리 및 코드 배치가 난감한 경우가 발생하게 됩니다.

이러한 이유를 가지고 해당 프로젝트를 멀티 모듈 프로젝트로 전환하려고 합니다!

_가장 큰 이유는 사이드 프로젝트이므로 도전해보고 싶은 마음이 있습니다_

아래의 사진은 다음과 같이 변경하려고 하는 아키텍처 설계도입니다.

<img src="https://private-user-images.githubusercontent.com/74192619/336103369-6faab452-b83c-4f07-9f90-2154dcc0c1fa.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTc0MjQ1MTAsIm5iZiI6MTcxNzQyNDIxMCwicGF0aCI6Ii83NDE5MjYxOS8zMzYxMDMzNjktNmZhYWI0NTItYjgzYy00ZjA3LTlmOTAtMjE1NGRjYzBjMWZhLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MDMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjAzVDE0MTY1MFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTYwM2Q0MGQwNTI5MDMwYmYwZjJiZDRiOWQ4NWZlYjY1ZDg4ZjY1OGNjMTU5MTlhZWE3MDNiMjFhYzczOTRiNDgmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.Fw5-XhGAL-Wxu_0BjJko5d8VmUuKyNzqYt43pgfZ93c" width="800">

다음 글에서는 단일 모듈 프로젝트에서 멀티 모듈 프로젝트로 전환하는 모든 과정에 대해서 작성해보겠습니다.

## Ref

- [Layered Architecture Deep Dive](https://msolo021015.medium.com/layered-architecture-deep-dive-c0a5f5a9aa37)
- [멀티모듈 설계 이야기 with Spring, Gradle](https://techblog.woowahan.com/2637/)