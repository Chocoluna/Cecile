---
title: NewsLetter
never_cache_twig: true
cache_enable: false
form:
    name: 'Liste de Mails'
    fields:
        -
            name: action
            type: radio
            label: Action
            default: subscribe
            options:
                subscribe: inscription
                unsubscribe: désinscription
            validate:
                required: true
        -
            name: email
            label: Email
            placeholder: mon@mail.com
            type: email
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Envoyer
    process:
        -
            redirect: '/newsletter?action={{ form.value.action }}&email={{ form.value.email }}'
---

<p style="text-align: center;">{{ subscriber() | raw}}</p>