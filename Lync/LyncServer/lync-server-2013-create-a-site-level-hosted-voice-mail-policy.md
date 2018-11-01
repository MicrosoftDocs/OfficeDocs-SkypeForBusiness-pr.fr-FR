---
title: "Créer une strat. de mess. vocale hébergée pour un site dans Lync Server 2013"
TOCtitle: "Créer une strat. de mess. vocale hébergée pour un site dans Lync Server 2013"
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398216(v=OCS.15)
ms:contentKeyID: 49296340
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer une stratégie de messagerie vocale hébergée pour un site dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-24_

Une stratégie de *site* peut concerner tous les utilisateurs qui sont hébergés sur le site pour lequel la stratégie est définie. Si aucune stratégie par utilisateur n’a été affectée à un utilisateur qui est configuré pour pouvoir accéder au service de messagerie unifiée Exchange hébergé, la stratégie de site s’applique. Si vous n’avez déployé aucune stratégie de site, la stratégie globale s’applique.

Pour plus d’informations sur la configuration des stratégies de site, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## Pour créer une stratégie de messagerie vocale hébergée pour un site

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsHostedVoicemailPolicy pour créer la stratégie. Par exemple, exécutez :
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Dans cet exemple, une stratégie de messagerie vocale hébergée est créée avec une étendue site et les paramètres suivants sont définis :
    
      - **Identity** spécifie un identificateur unique pour la stratégie qui englobe l’étendue. Pour une stratégie avec une étendue site, la valeur du paramètre Identity doit être spécifiée au format suivant : `site:`*\<nom\>*, par exemple, `site:Redmond`.
    
      - **Destination** spécifie le nom de domaine complet du service de messagerie unifiée Exchange hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée alors que la stratégie affectée à l’utilisateur n’a pas de valeur Destination, l’activation échoue.
    
      - **Description** fournit des informations facultatives décrivant la stratégie.
    
      - **Organization** fournit la liste des clients Exchange (séparés par des virgules) qui hébergent les utilisateurs de Lync Server 2013. Chaque client doit être spécifié avec son nom de domaine complet (FQDN) sur le service de messagerie unifiée Exchange hébergé.

