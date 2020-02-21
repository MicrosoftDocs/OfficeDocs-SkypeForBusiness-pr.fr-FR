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
ms.openlocfilehash: 8f7d061daedcdfabf4636c78a3a6a8bbe601903a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="87f1a-102">Vérifier l’accès par le biais de votre proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87f1a-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87f1a-103">_**Dernière modification de la rubrique :** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="87f1a-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="87f1a-p101">La procédure suivante vous permet de vérifier que vos utilisateurs peuvent accéder aux informations présentes sur le proxy inverse. Vous devrez peut-être finaliser la configuration du pare-feu et du DNS (Domain Name System) pour que l’accès fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="87f1a-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="87f1a-106">Pour vérifier que vous avez accès au site via Internet</span><span class="sxs-lookup"><span data-stu-id="87f1a-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="87f1a-107">Ouvrez un navigateur web et, dans la barre **Adresse**, tapez les URL que les clients utilisent pour accéder aux fichiers de carnet d’adresses et au site web de conférence, comme suit :</span><span class="sxs-lookup"><span data-stu-id="87f1a-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="87f1a-108">Pour le serveur de carnet d’adresses, tapez une URL semblable à **https://externalwebfarmFQDN/abs** la suivante : où nom est le nom de domaine complet externe des services Web externes qui hébergent les services de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="87f1a-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="87f1a-109">L’utilisateur doit recevoir une demande d’accès HTTP, car l’authentification Windows par défaut est configurée pour la sécurité du répertoire dans le dossier Serveur de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="87f1a-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="87f1a-110">Pour la Conférence, tapez une URL semblable à la suivante **https://externalwebfarmFQDN/meet** : où nom est le nom de domaine complet externe de la batterie de serveurs Web qui héberge le contenu de la réunion.</span><span class="sxs-lookup"><span data-stu-id="87f1a-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="87f1a-111">Cette URL doit afficher la page de dépannage pour la conférence.</span><span class="sxs-lookup"><span data-stu-id="87f1a-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="87f1a-112">Vous pouvez aussi confirmer que votre URL simple pour la conférence fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="87f1a-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="87f1a-113">Voici un exemple d’URL simple pour la participation à la Conférence.https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="87f1a-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="87f1a-114">Pour expansion du groupe de distribution, tapez une URL semblable à la **https://externalwebfarmFQDN/GroupExpansion/service.svc**suivante :.</span><span class="sxs-lookup"><span data-stu-id="87f1a-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="87f1a-115">L’utilisateur doit recevoir une demande d’accès HTTP, car l’authentification Windows par défaut est configurée pour la sécurité du répertoire dans le service de développement de groupes de distribution.</span><span class="sxs-lookup"><span data-stu-id="87f1a-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="87f1a-116">Pour les appels entrants, tapez l’URL simple semblable à la **https://externalwebfarmFQDN/dialin** suivante, où nom est le nom de domaine complet externe de la batterie de serveurs Web qui héberge la page de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="87f1a-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="87f1a-117">L’utilisateur doit être dirigé vers la page de numérotation.</span><span class="sxs-lookup"><span data-stu-id="87f1a-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="87f1a-118">Vous pouvez aussi confirmer que votre URL simple de numérotation fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="87f1a-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="87f1a-119">Un exemple d’URL simple pour l’accès à distance peut êtrehttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="87f1a-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="87f1a-120">Pour vérifier que l’URL de découverte automatique fonctionne, tapez https://lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="87f1a-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="87f1a-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="87f1a-121">externaldomainFQDN.</span></span> <span data-ttu-id="87f1a-122">Le navigateur doit vous inviter à ouvrir un fichier.</span><span class="sxs-lookup"><span data-stu-id="87f1a-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="87f1a-123">Sélectionnez Bloc-notes pour l’ouvrir.</span><span class="sxs-lookup"><span data-stu-id="87f1a-123">Select Notepad to open it.</span></span> <span data-ttu-id="87f1a-124">Une réponse typique est semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="87f1a-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

