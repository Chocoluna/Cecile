---
title: NewsLetter
process:
    markdown: true
    twig: true
cache_enable: false
form:
    name: Subscription
    fields:
        -
            name: action
            type: radio
            label: Choice
            default: subscribe
            options:
                subscribe: 's''inscrire'
                unsubscribe: 'Se désinscrire'
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

<p>{{ subscriber() | raw}}</p>