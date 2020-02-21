---
title: 'Lync Server 2013 : configuration de la découverte automatique pour les déploiements hybrides'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6015603d2c8c151cbe9d9b76410e51708f3ba9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Configuration de la découverte automatique dans Lync Server 2013 pour les déploiements hybrides

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-12_

Les déploiements hybrides sont des configurations qui utilisent à la fois le service Cloud de Microsoft Lync Online et le déploiement local. Dans ce type de configuration, le service de découverte automatique doit être capable de localiser l’emplacement actuel de l’utilisateur. Cela signifie que la découverte automatique facilite la recherche du compte d’utilisateur et l’emplacement du serveur qui héberge le compte de l’utilisateur, qu’il se trouve dans le déploiement local ou dans le déploiement Lync Online.

Par exemple, si un compte d’utilisateur est hébergé sur un serveur dans Lync Online, la tentative de localisation de l’utilisateur se déroule comme suit, dans un processus appelé « *détectabilité*» :

  - L’utilisateur lance une tentative de connexion au déploiement sur site, **contoso.com**.

  - La tentative est envoyée à lyncdiscover.contoso.com, le nom de DNS associé au service de découverte automatique.

  - La découverte automatique fait référence au pool de serveurs d’inscriptions supposés au niveau du déploiement contoso.com sur site et reçoit des informations sur le serveur d’accueil réel de l’utilisateur hébergé dans Lync Online. Le service de découverte automatique envoie ensuite à l’utilisateur une référence vers le service de découverte automatique en ligne **lync.com**.

  - L’utilisateur lance une tentative de connexion vers le service de découverte automatique en ligne lync.com et peut localiser le compte et le serveur d’hébergement de l’utilisateur.

Pour permettre aux clients de découvrir le déploiement où se trouve le serveur d’accueil de l’utilisateur, vous devez configurer le service de découverte automatique avec une nouvelle URL (Uniform Resource Locator). Pour configurer le service de découverte automatique, procédez comme suit :

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configuration du service de découverte automatique pour les déploiements hybrides

1.  Dans la rubrique [configuration du service de découverte automatique requise pour Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), vous utilisez Get-CsHostingProvider pour récupérer la valeur de l’attribut ProxyFQDN.

2.  À partir de Lync Server Management Shell, tapez
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Où \[Identity\] est remplacé par le nom de domaine de l’espace d’adressage SIP partagé.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

