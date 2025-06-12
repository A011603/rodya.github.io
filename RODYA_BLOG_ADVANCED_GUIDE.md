
# 🌟 Rodya's Advanced Blog Customization Guide

이 문서는 **Rodya Hates Math** 블로그를 더욱 깊이 있게 커스터마이징하는 방법을 정리한 고급 설정 가이드입니다.

---

## 🎨 고급 스타일 조정 (SCSS)

`assets/css/custom.scss`를 통해 아래와 같은 설정이 가능합니다.

### 1. 전체 레이아웃 너비 조정

```scss
.page {
  max-width: 1000px;
  margin: 0 auto;
}
```

### 2. 글 본문만 넓히기

```scss
.page__content {
  max-width: 800px;
}
```

### 3. 코드 블럭 색상 변경

```scss
.highlighter-rouge {
  background-color: #f4f4f4;
  border-left: 5px solid #d6336c;
  padding: 1rem;
}
```

---

## 🖋 수식 스타일 변경

`MathJax` 기본 스타일은 너무 작게 보일 수 있습니다.

```css
mjx-container {
  font-size: 110% !important;
}
```

→ 이 스타일은 `custom.html`에 `<style>` 태그로 삽입하거나, CSS에 추가하세요.

---

## 🧭 네비게이션 메뉴 커스터마이징

`_data/navigation.yml` 파일을 만들어 다음과 같이 설정 가능:

```yaml
main:
  - title: "Home"
    url: /
  - title: "Tags"
    url: /tags/
  - title: "About"
    url: /about/
```

> `_config.yml`에 `navigation:` 항목도 함께 지정해야 함.

---

## 📚 포스트 목록을 카드로 표시하고 싶다면

`_config.yml`에 다음 옵션 추가:

```yaml
author_profile: true
paginate: 5
paginate_path: /page:num/
```

---

## 🧪 커스텀 포스트 템플릿 만들기

`_layouts/post.html` 복사 후 수정 → 원하는 구조로 재구성

예: 수식이 항상 보이게 하기, 날짜 대신 태그 먼저 보이게 하기 등

---

## 🌈 다크 모드 지원 추가 (선택적)

`assets/css/custom.scss`에 다음 코드 추가:

```scss
@media (prefers-color-scheme: dark) {
  body {
    background-color: #111;
    color: #eee;
  }

  a {
    color: #88f;
  }
}
```

---

## 💬 댓글 기능 추가 (Utterances)

1. GitHub 저장소 만들기 (댓글 저장용)
2. `_includes/comments.html` 파일 생성 후 아래 코드 삽입:

```html
<script src="https://utteranc.es/client.js"
        repo="yourname/your-repo"
        issue-term="pathname"
        label="💬 comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
```

3. `post.html` 레이아웃 파일에서 `{{ content }}` 아래에 `{% include comments.html %}` 삽입

---

## 🔍 SEO / 메타태그

`_config.yml`에:

```yaml
seo:
  type: "Blog"
  name: "Rodya Hates Math"
  description: "Math blog with LaTeX & wonder"
```

그리고 `jekyll-seo-tag`를 활성화하면 meta 태그가 자동 삽입됨.

---

## 🔄 자동 배포 테스트

파일 변경 후 GitHub에 푸시하면 GitHub Actions가 자동으로 다시 빌드하고 배포합니다.  
시간이 오래 걸릴 경우 → 빈 파일 하나 생성해서 다시 푸시하면 트리거 가능.

---

## 🙌 도움말

- [Minimal Mistakes Docs](https://mmistakes.github.io/minimal-mistakes/docs/)
- [Jekyll Docs](https://jekyllrb.com/docs/)
- [MathJax Docs](https://docs.mathjax.org/)
- [SCSS Cheatsheet](https://sass-lang.com/guide)

---

꾸미는 것도 수학만큼 재밌을 수 있어요 😉  
- by Rodya
