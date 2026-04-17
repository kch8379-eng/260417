[README.md](https://github.com/user-attachments/files/26827280/README.md)
# 📄 AI 보고서 생성기 (AI Report Generator)

사용자가 제공한 보고서 양식(템플릿)의 구조와 형식을 학습하여, **새로운 내용이 포함된 동일한 양식의 보고서를 자동으로 작성**해주는 단일 페이지 웹앱(SPA)입니다. 별도의 백엔드 서버 없이 브라우저에서 직접 Google Gemini API와 통신하여 작동합니다.

## ✨ 주요 기능
- **API Key 안전 보관**: 사용자의 Gemini API Key를 브라우저 `localStorage`에만 저장하여 외부 유출 위험이 없습니다.
- **다양한 양식 포맷 지원**: 텍스트(.txt, .md, .html) 파일 및 이미지(jpg, png, webp 등) 기반 템플릿 업로드를 모두 지원합니다.
- **맞춤형 텍스트 생성**: 양식의 구조, 섹션, 문체를 완벽하게 모방하여 마크다운 형태의 새 보고서를 작성합니다.
- **자동 표지 이미지 생성**: 보고서의 제목 및 주제를 바탕으로 전문적이고 고급스러운 디자인의 표지용 일러스트레이션을 자동으로 알아서 생성합니다.
- **즉시 내보내기**: 생성된 텍스트와 이미지를 원클릭으로 클립보드에 복사하거나 `.txt` 파일로 다운로드할 수 있습니다.

## 🛠 기술 스택
- **언어 및 제약**: HTML5, CSS3, Vanilla JavaScript (ES2020+) 단일 파일(`index.html`)
- **스타일링**: 순수 CSS 적용 (고급스러운 황금빛 다크 테마)
- **비동기 통신**: Fetch API
- **폰트**: Google Fonts (Inter, Fira Code, Merriweather)
- **배포**: Netlify (Netlify.toml 설정을 통한 빠른 정적 배포 최적화)

## 🤖 사용된 AI 모델 (Gemini API)
- **텍스트 생성**: `gemini-3.1-flash-lite-preview`
- **이미지 생성**: `gemini-3.1-flash-image-preview`
> *모든 API 호출은 로컬에서 직접 처리되며 사용자의 데이터가 앱의 서버를 경유하지 않습니다.*

## 🚀 로컬 실행 방법
이 프로젝트는 외부 의존성이나 빌드 과정 없이 동작하므로, 어떠한 서버 환경 세팅도 필요하지 않습니다.

1. 이 저장소를 로컬 머신에 다운로드하거나 Clone 합니다.
2. 폴더 내의 `index.html` 파일을 더블 클릭하거나 가장 즐겨쓰시는 웹 브라우저 창(Chrome, Edge, Safari 등)으로 드래그 앤 드롭 합니다.
3. 브라우저에서 웹앱이 실행되면 Gemini API Key를 입력 후 즉시 사용하실 수 있습니다!

## 🌐 Netlify 수동 배포 안내
저장소의 파일을 수정 없이 인터넷에 즉시 배포하여 누구나 접근할 수 있도록 만들고 싶다면 아래 단계를 따르세요.

1. `index.html`과 `netlify.toml` 파일이 같은 폴더 위치에 있는지 확인합니다.
2. [Netlify 홈페이지](https://netlify.com/)에 접속하여 로그인합니다.
3. **Sites** 메뉴에서 하단의 **Deploy manually** 영역을 찾습니다. (또는 'Add new site' > 'Deploy manually')
4. 이 프로젝트 폴더(`.git` 폴더가 포함되었거나 `index.html`이 있는 디렉토리 전체)를 회색 점선 영역(Drag and drop)으로 끌어다 놓습니다.
5. 몇 초 뒤 바로 라이브 서버에 반영되며 Netlify가 제공하는 URL을 통해 접속할 수 있습니다.

---
**Disclaimer**: 이 애플리케이션은 Gemini API를 활용하기 위해 직접 발급받은 API 키가 필요합니다. 과도한 API 호출 시 Google Cloud의 사용 한도 제한이 발생할 수 있습니다.
