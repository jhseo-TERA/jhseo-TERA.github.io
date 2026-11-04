# Analog IC Design · jhseo-TERA

개인 공부와 직접 쓰는 교재를 위한 독립적인 Quarto 사이트입니다.

- 사이트 주소: https://analog.jhseo-archive.com/
- GitHub Pages 기본 주소: https://jhseo-tera.github.io/
- 운영자: [jhseo-TERA](https://github.com/jhseo-TERA)

## 파일과 역할

| 파일 | 역할 |
|---|---|
| `index.qmd` | 첫 화면 |
| `textbook/index.qmd` | 교재 안내와 학습 순서 |
| `textbook/01-operating-point.qmd` | 첫 장의 작성 예시 |
| `notes/index.qmd` | 학습 노트 목록 |
| `references.qmd` | 참고자료 |
| `about.qmd` | 사이트 소개 |
| `_quarto.yml` | 이름, 주소, 메뉴, 목차, 테마 |
| `styles.css` | 색상, 글꼴과 레이아웃 |
| `assets/` | 직접 만든 그림과 아이콘 |
| `templates/` | 새 장과 노트 작성 양식 |
| `.github/workflows/publish.yml` | 자동 빌드와 배포 |

## GitHub에서 수정

1. 수정할 `.qmd` 파일을 열고 **Edit this file**을 누릅니다.
2. Markdown으로 본문을 작성합니다. 수식은 `$...$`, 독립 수식은 `$$...$$`를 사용합니다.
3. **Commit changes**로 `main`에 저장합니다.
4. Actions의 **Publish personal archive**가 성공하면 사이트에 반영됩니다.

각 글 아래의 편집 링크에서도 소스로 바로 이동할 수 있습니다.
현재 첫 장은 설명용 작성 예시이며, 개인의 실제 연구나 시뮬레이션 결과로 표시하지 않았습니다.

## 새 교재 장 추가

`templates/_chapter.qmd`를 복사해 `textbook/02-amplifier.qmd`처럼 저장합니다.
내용을 쓴 다음 `_quarto.yml`의 `website.sidebar` 아래 교재 목차에 추가합니다.
`textbook/index.qmd`의 목록도 함께 갱신합니다.

## 새 노트 추가

`templates/_note.qmd`를 복사해 `notes/my-note.qmd`처럼 저장하고 날짜와 내용을 작성합니다.
`notes/index.qmd`에 `[노트 제목](my-note.qmd)` 링크를 추가합니다.
새 `.qmd` 파일은 자동 빌드 대상에 포함됩니다.

## 로컬 미리보기

[Quarto](https://quarto.org/docs/get-started/)를 설치한 뒤 프로젝트 폴더에서 실행합니다.

```sh
quarto preview
```

완성된 HTML을 생성하려면 `quarto render`를 실행합니다. 결과는 `_site/`에 생성됩니다.
현재 글은 실행 코드가 없는 문서이므로 Python, R, LaTeX 설치가 필요하지 않습니다.
코드 실행 기능을 쓰려면 필요한 실행 환경을 추가하고 `_quarto.yml`의 `execute.enabled`를 변경합니다.

## 배포와 도메인

GitHub **Settings → Pages → Source**를 **GitHub Actions**로 설정합니다.
Custom domain은 `analog.jhseo-archive.com`입니다.
Cloudflare DNS에서 `analog`의 CNAME 대상을 `jhseo-tera.github.io`로 설정합니다.
인증서 발급과 GitHub 도메인 확인을 위해 DNS only로 연결합니다.

서브도메인을 바꾸면 GitHub Pages의 Custom domain, DNS 레코드, `_quarto.yml`의 `website.site-url`, `CNAME`을 함께 바꿉니다.

## 출처

참고한 강의는 `references.qmd`와 해당 글에 링크합니다. 이 저장소는 기존 강의 저장소의 포크가 아닙니다.
직접 작성한 문서, 스타일과 SVG로 구성되며 Quarto가 탐색·검색·수식 표시 기능을 생성합니다.
