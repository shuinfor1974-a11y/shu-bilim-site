backend:
  name: git-gateway
  branch: main

media_folder: "assets/uploads"
public_folder: "/assets/uploads"

locale: "kk"

collections:
  - name: "news"
    label: "Жаңалықтар"
    folder: "news"
    create: true
    slug: "{{year}}-{{month}}-{{day}}-{{slug}}"
    fields:
      - { label: "Тақырып", name: "title", widget: "string" }
      - { label: "Күні", name: "date", widget: "datetime", format: "YYYY-MM-DD" }
      - { label: "Сурет", name: "image", widget: "image", required: false }
      - { label: "Қысқаша мәтін", name: "summary", widget: "text" }
      - { label: "Толық мәтін", name: "body", widget: "markdown" }

  - name: "pages"
    label: "Беттер"
    files:
      - label: "Бөлім туралы"
        name: "about"
        file: "content/about.md"
        fields:
          - { label: "Тақырып", name: "title", widget: "string" }
          - { label: "Мәтін", name: "body", widget: "markdown" }
      - label: "Байланыс"
        name: "contacts"
        file: "content/contacts.md"
        fields:
          - { label: "Мекенжай", name: "address", widget: "string" }
          - { label: "Телефон", name: "phone", widget: "string" }
          - { label: "Email", name: "email", widget: "string" }
