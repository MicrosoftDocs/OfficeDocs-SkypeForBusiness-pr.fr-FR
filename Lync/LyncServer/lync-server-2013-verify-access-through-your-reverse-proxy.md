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

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="7db78-102">Vérification de l’accès avec le proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7db78-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7db78-103">_**Dernière modification de la rubrique :** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="7db78-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="7db78-104">Utilisez la procédure suivante pour vérifier que vos utilisateurs peuvent accéder aux informations sur le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="7db78-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="7db78-105">Vous devrez peut-être effectuer la configuration de pare-feu et la configuration de DNS (Domain Name System) pour que Access fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="7db78-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="7db78-106">Pour vérifier que vous pouvez accéder au site Web via Internet</span><span class="sxs-lookup"><span data-stu-id="7db78-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="7db78-107">Ouvrez un navigateur Web, tapez les URL de la barre d' **adresse** que les clients utilisent pour accéder aux fichiers du carnet d’adresses et au site Web pour les conférences comme suit :</span><span class="sxs-lookup"><span data-stu-id="7db78-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="7db78-108">Pour le serveur du carnet d’adresses, tapez une URL semblable à **https://externalwebfarmFQDN/abs** ce qui suit : où externalwebfarmFQDN est le nom de domaine complet (FQDN) du service Web externe qui héberge les services du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="7db78-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="7db78-109">L’utilisateur doit être confronté à un défi HTTP, car la sécurité d’annuaire dans le dossier serveur du carnet d’adresses est configurée par défaut sur authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="7db78-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="7db78-110">Pour Conférence, tapez une URL semblable à ce qui suit **https://externalwebfarmFQDN/meet** : où externalwebfarmFQDN est le nom de domaine complet externe de la batterie de serveurs Web qui héberge le contenu de la réunion.</span><span class="sxs-lookup"><span data-stu-id="7db78-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="7db78-111">Cette URL doit afficher la page de résolution des problèmes pour les conférences.</span><span class="sxs-lookup"><span data-stu-id="7db78-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="7db78-112">Vous pouvez également vérifier que votre URL simple pour les conférences fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="7db78-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="7db78-113">Un exemple d’URL simple pour la participation à la Conférence peut êtrehttps://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7db78-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="7db78-114">Pour extension du groupe de distribution, tapez une URL semblable à ce **https://externalwebfarmFQDN/GroupExpansion/service.svc**qui suit :.</span><span class="sxs-lookup"><span data-stu-id="7db78-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="7db78-115">L’utilisateur doit recevoir un défi HTTP, car la sécurité d’annuaire sur le service d’extension du groupe de distribution est configurée par défaut sur l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="7db78-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="7db78-116">Pour composer un numéro de téléphone, tapez l’URL simple semblable à **https://externalwebfarmFQDN/dialin** la suivante, où externalwebfarmFQDN est le nom de domaine complet (FQDN) externe de la batterie de serveurs Web qui héberge la page de conférence rendez-vous pour la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="7db78-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="7db78-117">L’utilisateur doit être dirigé vers la page de connexion.</span><span class="sxs-lookup"><span data-stu-id="7db78-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="7db78-118">Vous pouvez également vérifier que votre URL de connexion simple fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="7db78-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="7db78-119">Un exemple d’URL simple pour les appels entrants peut êtrehttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7db78-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="7db78-120">Pour confirmer le fonctionnement de l’URL de découverte automatique, https://lyncdiscovertapez.</span><span class="sxs-lookup"><span data-stu-id="7db78-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="7db78-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="7db78-121">externaldomainFQDN.</span></span> <span data-ttu-id="7db78-122">Le navigateur doit vous inviter à ouvrir un fichier.</span><span class="sxs-lookup"><span data-stu-id="7db78-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="7db78-123">Sélectionnez Bloc-notes pour l’ouvrir.</span><span class="sxs-lookup"><span data-stu-id="7db78-123">Select Notepad to open it.</span></span> <span data-ttu-id="7db78-124">Une réponse classique serait semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="7db78-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

