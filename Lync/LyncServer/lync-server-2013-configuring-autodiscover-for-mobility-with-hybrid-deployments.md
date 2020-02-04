---
title: Configuration de la découverte automatique pour la mobilité avec les déploiements hybrides
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd6c36afb89d1a8b354d072ee39ee3f6a2e7e93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Configuration de la découverte automatique dans Lync Server 2013 pour la mobilité avec les déploiements hybrides

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-18_

Les déploiements hybrides sont des configurations utilisant à la fois le service de Cloud Computing Microsoft Lync Online et le déploiement local. Dans ce type de configuration, le service de découverte automatique doit être en mesure de localiser l’emplacement où l’utilisateur se trouve réellement. Par exemple, la fonction de découverte automatique facilite la recherche du compte d’utilisateur et l’emplacement du serveur qui héberge le compte de l’utilisateur, même s’il se trouve dans le déploiement local ou dans le déploiement Lync Online.

Par exemple, si le compte d’un utilisateur est hébergé sur un serveur dans Lync Online, la tentative de localisation de l’utilisateur se déroule comme suit, dans un processus connu sous le nom de *découverte*:

  - Un utilisateur commence une tentative de connexion à un déploiement local, **contoso.com**.

  - La tentative est envoyée à lyncdiscover.contoso.com, le nom DNS associé au service de découverte automatique.

  - La découverte automatique fait référence au pool d’inscriptions présumées au niveau du déploiement local de contoso.com et dispose d’informations sur le véritable serveur d’accueil hébergé dans Lync Online. La découverte automatique envoie ensuite à l’utilisateur une référence au service de découverte automatique **Lync.com** online.

  - L’utilisateur entame une tentative de connexion au service de découverte automatique lync.com Online et est en mesure de trouver le compte de l’utilisateur et le serveur associé de l’utilisateur.

Pour permettre aux clients mobiles de découvrir le déploiement sur lequel se trouve le serveur associé de l’utilisateur, vous devez configurer le service de découverte automatique à l’aide d’une nouvelle URL (Uniform Resource Locator). Procédez comme suit pour configurer le service de découverte automatique.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configuration de la découverte automatique pour les déploiements hybrides

1.  Vous utilisez Get-CsHostingProvider pour récupérer la valeur de l’attribut ProxyFQDN.

2.  À partir de Lync Server Management Shell, tapez
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Où \[Identity\] est remplacé par le nom de domaine de l’espace d’adressage SIP partagé.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

