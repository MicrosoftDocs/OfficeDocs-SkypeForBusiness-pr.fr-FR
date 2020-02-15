---
title: 'Lync Server 2013 : vérification de l’accès par le biais de votre proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec8a6d5339af93a7e8c0f63aca5f5d3f990583
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Vérifier l’accès par le biais de votre proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-29_

La procédure suivante vous permet de vérifier que vos utilisateurs peuvent accéder aux informations présentes sur le proxy inverse. Vous devrez peut-être finaliser la configuration du pare-feu et du DNS (Domain Name System) pour que l’accès fonctionne correctement.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Pour vérifier que vous avez accès au site via Internet

  - Ouvrez un navigateur web et, dans la barre **Adresse**, tapez les URL que les clients utilisent pour accéder aux fichiers de carnet d’adresses et au site web de conférence, comme suit :
    
      - Pour le serveur de carnet d’adresses, tapez une URL semblable à **https://externalwebfarmFQDN/abs** la suivante : où nom est le nom de domaine complet externe des services Web externes qui hébergent les services de carnet d’adresses. L’utilisateur doit recevoir une demande d’accès HTTP, car l’authentification Windows par défaut est configurée pour la sécurité du répertoire dans le dossier Serveur de carnet d’adresses.
    
      - Pour la Conférence, tapez une URL semblable à la suivante **https://externalwebfarmFQDN/meet** : où nom est le nom de domaine complet externe de la batterie de serveurs Web qui héberge le contenu de la réunion. Cette URL doit afficher la page de dépannage pour la conférence. Vous pouvez aussi confirmer que votre URL simple pour la conférence fonctionne correctement. Voici un exemple d’URL simple pour la participation à la Conférence.https://meet.contoso.com
    
      - Pour expansion du groupe de distribution, tapez une URL semblable à la **https://externalwebfarmFQDN/GroupExpansion/service.svc**suivante :. L’utilisateur doit recevoir une demande d’accès HTTP, car l’authentification Windows par défaut est configurée pour la sécurité du répertoire dans le service de développement de groupes de distribution.
    
      - Pour les appels entrants, tapez l’URL simple semblable à la **https://externalwebfarmFQDN/dialin** suivante, où nom est le nom de domaine complet externe de la batterie de serveurs Web qui héberge la page de conférence rendez-vous. L’utilisateur doit être dirigé vers la page de numérotation. Vous pouvez aussi confirmer que votre URL simple de numérotation fonctionne correctement. Un exemple d’URL simple pour l’accès à distance peut êtrehttps://dialin.contoso.com
    
      - Pour vérifier que l’URL de découverte automatique fonctionne, tapez https://lyncdiscover. externaldomainFQDN. Le navigateur doit vous inviter à ouvrir un fichier. Sélectionnez Bloc-notes pour l’ouvrir. Une réponse typique est semblable à la suivante :
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

