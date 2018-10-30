---
title: "Conf. de la redirection vers la messagerie vocale dans Lync Server 2013"
TOCtitle: "Conf. de la redirection vers la messagerie vocale dans Lync Server 2013"
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49891469
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la redirection vers la messagerie vocale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Lorsqu’un utilisateur configure la sonnerie simultanée sur un téléphone mobile, un appelant est généralement acheminé vers la messagerie vocale personnelle de l’utilisateur si le téléphone mobile est éteint, n’a plus de batterie ou est hors réseau. Avec Microsoft Lync Server 2013, les utilisateurs peuvent choisir de faire acheminer les appels professionnels vers leur système de messagerie vocale d’entreprise. Plus spécifiquement, vous pouvez définir un minuteur et si le système de messagerie vocale de l’opérateur répond à l’appel dans les délais définis, Lync Server 2013 se déconnecte du système de messagerie vocale de l’opérateur (et de la messagerie vocale personnelle de l’utilisateur), tandis que les points de terminaison restants de l’utilisateur dans le système d’entreprise continuent de sonner. De cette manière, l’appelant est acheminé automatiquement vers la messagerie vocale d’entreprise de l’utilisateur.

Cette configuration s’effectue à l’aide de l’applet de commande Lync Server Management Shell Set-CsVoicePolicy, au niveau de la stratégie de voix, avec les paramètres suivants.

## Configurer l’échappement de messagerie vocale

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Spécifiez les paramètres suivants de **Set-CsVoicePolicy** :
    
      - **EnableVoicemailEscapeTimer** - Active ou désactive le minuteur d’échappement.
    
      - **PSTNVoicemailEscapeTimer** - Spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8000 millisecondes.

## Exemple

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

## Voir aussi

#### Autres ressources

[Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

