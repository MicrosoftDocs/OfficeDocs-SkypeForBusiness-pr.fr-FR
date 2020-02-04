---
title: 'Lync Server 2013 : configuration de l’échappement de la messagerie vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c32d3bbc39d8f18e30153193c1e722db1ec9d50e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Configuration de l’échappement de la messagerie vocale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Lorsqu’un utilisateur configure la sonnerie simultanée sur un téléphone mobile, un appelant est généralement routé vers la messagerie vocale personnelle de l’utilisateur si le téléphone mobile est éteint, n’a plus de batterie ou est hors réseau. Avec Lync Server 2013, les utilisateurs peuvent choisir de faire Router leurs appels d’entreprise vers leur système de messagerie vocale. Plus précisément, un minuteur peut être configuré, et si l’appel est reçu par la messagerie vocale de l’opérateur dans la plage de temps définie, Lync Server se déconnecte du système de messagerie vocale de l’opérateur (et de la messagerie vocale personnelle de l’utilisateur), tandis que l’utilisateur reste les points de terminaison du système d’entreprise continuent de sonner. De cette manière, l’appelant est acheminé automatiquement vers la messagerie vocale d’entreprise de l’utilisateur.

Cette configuration est effectuée à l’aide de l’applet de commande Lync Server Management Shell, **Set-CsVoicePolicy**, au niveau de la stratégie vocale, avec les paramètres suivants.

<div>

## <a name="to-configure-voice-mail-escape"></a>Pour configurer la redirection vers la messagerie vocale

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Spécifiez les paramètres ci-dessous sur **Set-CsVoicePolicy** :
    
      - **EnableVoicemailEscapeTimer** : active ou désactive le minuteur de redirection.
    
      - **PSTNVoicemailEscapeTimer** : spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1 500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8 000 millisecondes.

</div>

<div>

## <a name="example"></a>Exemple

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

