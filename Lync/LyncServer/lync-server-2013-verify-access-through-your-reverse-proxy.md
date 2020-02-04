---
title: 'Lync Server 2013 : Vérification de l’accès avec le proxy inverse'
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
ms.openlocfilehash: e13f7e23f3404191f7251c1f49bda6f8935a2929
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Vérification de l’accès avec le proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-29_

Utilisez la procédure suivante pour vérifier que vos utilisateurs peuvent accéder aux informations sur le proxy inverse. Vous devrez peut-être effectuer la configuration de pare-feu et la configuration de DNS (Domain Name System) pour que Access fonctionne correctement.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Pour vérifier que vous pouvez accéder au site Web via Internet

  - Ouvrez un navigateur Web, tapez les URL de la barre d' **adresse** que les clients utilisent pour accéder aux fichiers du carnet d’adresses et au site Web pour les conférences comme suit :
    
      - Pour le serveur du carnet d’adresses, tapez une URL semblable à **https://externalwebfarmFQDN/abs** ce qui suit : où externalwebfarmFQDN est le nom de domaine complet (FQDN) du service Web externe qui héberge les services du carnet d’adresses. L’utilisateur doit être confronté à un défi HTTP, car la sécurité d’annuaire dans le dossier serveur du carnet d’adresses est configurée par défaut sur authentification Windows.
    
      - Pour Conférence, tapez une URL semblable à ce qui suit **https://externalwebfarmFQDN/meet** : où externalwebfarmFQDN est le nom de domaine complet externe de la batterie de serveurs Web qui héberge le contenu de la réunion. Cette URL doit afficher la page de résolution des problèmes pour les conférences. Vous pouvez également vérifier que votre URL simple pour les conférences fonctionne correctement. Un exemple d’URL simple pour la participation à la Conférence peut êtrehttps://meet.contoso.com
    
      - Pour extension du groupe de distribution, tapez une URL semblable à ce **https://externalwebfarmFQDN/GroupExpansion/service.svc**qui suit :. L’utilisateur doit recevoir un défi HTTP, car la sécurité d’annuaire sur le service d’extension du groupe de distribution est configurée par défaut sur l’authentification Windows.
    
      - Pour composer un numéro de téléphone, tapez l’URL simple semblable à **https://externalwebfarmFQDN/dialin** la suivante, où externalwebfarmFQDN est le nom de domaine complet (FQDN) externe de la batterie de serveurs Web qui héberge la page de conférence rendez-vous pour la Conférence rendez-vous. L’utilisateur doit être dirigé vers la page de connexion. Vous pouvez également vérifier que votre URL de connexion simple fonctionne correctement. Un exemple d’URL simple pour les appels entrants peut êtrehttps://dialin.contoso.com
    
      - Pour confirmer le fonctionnement de l’URL de découverte automatique, https://lyncdiscovertapez. externaldomainFQDN. Le navigateur doit vous inviter à ouvrir un fichier. Sélectionnez Bloc-notes pour l’ouvrir. Une réponse classique serait semblable à ce qui suit :
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

