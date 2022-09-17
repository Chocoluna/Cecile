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

<script>
function maillist_action(action, email, mailing=null)
{
   if( action == 'subscribe' || action == 'unsubscribe' ){
       var url = "https://cecile.dev.coutupetra.fr/newsletter?action=" + action + "&email=" + email
       if ( mailing != null ) url += "&mailing=" + mailing

       var xmlHttp = new XMLHttpRequest();
       xmlHttp.open( "GET", url, false );
       xmlHttp.send( null );
       return true;
   }
   else
      return false;
}
</script>
