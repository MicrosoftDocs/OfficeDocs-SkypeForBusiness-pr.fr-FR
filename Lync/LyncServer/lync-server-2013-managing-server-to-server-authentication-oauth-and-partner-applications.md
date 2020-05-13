---
title: Gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f3f32b4e0c13ea68df183d19b020118e32205b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="ea807-102">Gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea807-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea807-103">_**Dernière modification de la rubrique :** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="ea807-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="ea807-104">Microsoft Lync Server 2013 doit être en mesure de communiquer de manière sécurisée avec d’autres applications et produits serveurs.</span><span class="sxs-lookup"><span data-stu-id="ea807-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="ea807-105">Par exemple, vous pouvez configurer Lync Server 2013 de manière à ce que les données de contact et/ou les données d’archivage soient stockées dans Microsoft Exchange Server 2013 ; Toutefois, cette opération ne peut être réalisée que si Lync Server et Exchange sont en mesure de communiquer de manière sécurisée.</span><span class="sxs-lookup"><span data-stu-id="ea807-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="ea807-106">De même, vous pouvez planifier une conférence Lync Server à partir de Microsoft SharePoint Server. Cependant, cette opération ne peut être réalisée que si les deux serveurs (SharePoint et Lync Server) s’approuvent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="ea807-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="ea807-107">Bien qu’il soit possible d’utiliser un mécanisme d’authentification pour la communication Lync à Exchange et un mécanisme distinct pour la communication Lync à SharePoint, une approche plus efficace consiste à utiliser une méthode standardisée pour l’authentification et l’autorisation de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="ea807-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="ea807-108">L’utilisation d’une méthode standardisée unique pour l’authentification de serveur à serveur est l’approche adoptée par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea807-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="ea807-109">Pour la version 2013, Lync Server 2013 (ainsi que d’autres produits serveur Microsoft, y compris Exchange 2013 et Microsoft SharePoint Server) prennent en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="ea807-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="ea807-110">Avec OAuth, un protocole d’autorisation standard utilisé par un certain nombre de sites principaux, les informations d’identification de l’utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre.</span><span class="sxs-lookup"><span data-stu-id="ea807-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="ea807-111">Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; Ces jetons accordent l’accès à un ensemble spécifique de ressources pour une durée spécifique.</span><span class="sxs-lookup"><span data-stu-id="ea807-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="ea807-112">L’authentification OAuth implique généralement trois parties : un serveur d’autorisation unique et les deux domaines qui doivent communiquer les uns avec les autres.</span><span class="sxs-lookup"><span data-stu-id="ea807-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="ea807-113">(Vous pouvez également effectuer l’authentification de serveur à serveur sans utiliser de serveur d’autorisation, un processus qui sera abordé plus loin dans ce document.) Les jetons de sécurité sont émis par le serveur d’autorisation (également appelé serveur de jetons de sécurité) pour les deux domaines qui doivent communiquer ; Ces jetons vérifient que les communications provenant d’un domaine doivent être approuvées par l’autre domaine.</span><span class="sxs-lookup"><span data-stu-id="ea807-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="ea807-114">Par exemple, le serveur d’autorisation peut émettre des jetons qui vérifient que les utilisateurs d’un domaine Lync Server 2013 spécifique sont en mesure d’accéder à un domaine Exchange 2013 spécifié, et inversement.</span><span class="sxs-lookup"><span data-stu-id="ea807-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ea807-115">Un domaine est tout simplement un conteneur de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ea807-115">A realm is simply a security container.</span></span> <span data-ttu-id="ea807-116">Par défaut, Lync Server 2013 utilise votre domaine SIP par défaut comme domaine OAuth.</span><span class="sxs-lookup"><span data-stu-id="ea807-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="ea807-117">Des espaces de noms SIP supplémentaires sont ajoutés à la liste autre nom de l’objet dans le certificat OAuth.</span><span class="sxs-lookup"><span data-stu-id="ea807-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="ea807-118">Lync Server 2013 prend en charge trois scénarios d’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="ea807-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="ea807-119">Avec Lync Server 2013, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="ea807-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="ea807-120">Configurez l’authentification de serveur à serveur entre une installation locale de Lync Server 2013 et une installation locale d’Exchange 2013 et/ou de Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ea807-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="ea807-121">Configurez l’authentification de serveur à serveur entre une paire de composants Microsoft 365 (par exemple, entre Microsoft Exchange et Microsoft Lync Server, ou entre Microsoft Lync Server et Microsoft SharePoint).</span><span class="sxs-lookup"><span data-stu-id="ea807-121">Configure server-to-server authentication between a pair of Microsoft 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="ea807-122">Configurez l’authentification de serveur à serveur dans un environnement intersite (c’est-à-dire, l’authentification de serveur à serveur entre un serveur local et un composant Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="ea807-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Microsoft 365 component).</span></span>

<span data-ttu-id="ea807-123">Notez que, à ce stade, seuls Exchange 2013, SharePoint Server et Lync Server 2013 prennent en charge l’authentification de serveur à serveur ; Si vous n’exécutez pas l’un de ces serveurs, vous ne serez pas en mesure d’implémenter entièrement l’authentification OAuth.</span><span class="sxs-lookup"><span data-stu-id="ea807-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="ea807-124">Il est également important de noter que vous n’avez pas besoin d’utiliser l’authentification de serveur à serveur : l’authentification de serveur à serveur n’est pas nécessaire pour déployer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea807-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="ea807-125">Si Lync Server 2013 n’a pas besoin de communiquer avec d’autres serveurs (par exemple, Exchange 2013), l’authentification de serveur à serveur n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ea807-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="ea807-126">Toutefois, l’authentification de serveur à serveur est requise si vous voulez utiliser certaines des nouvelles fonctionnalités de Lync Server, telles que le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="ea807-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="ea807-127">Avec le magasin de contacts unifié, les informations de contact de Lync Server 2013 sont stockées dans Exchange 2013 et non dans Lync Server ; Cela permet aux utilisateurs de disposer d’un seul ensemble de contacts directement accessible à partir de Lync, de Microsoft Outlook ou de Microsoft Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="ea807-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="ea807-128">Étant donné que le magasin de contacts unifié nécessite que Lync Server 2013 partage des informations avec Exchange 2013, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ea807-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="ea807-129">L’authentification de serveur à serveur est également requise si vous choisissez d’utiliser l’archivage Exchange, dans lequel les transcriptions des sessions de messagerie instantanée sont enregistrées en tant qu’e-mails Exchange 2013 et non en tant qu’enregistrements de base de données individuels.</span><span class="sxs-lookup"><span data-stu-id="ea807-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="ea807-130">Pour que la version Microsoft 365 de Lync Server communique avec son homologue Exchange, Lync Server 2013 doit d’abord obtenir un jeton de sécurité à partir du serveur d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="ea807-130">For the Microsoft 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="ea807-131">Lync Server utilise ensuite ce jeton de sécurité pour s’identifier auprès d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="ea807-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="ea807-132">La version 365 de Microsoft Exchange doit suivre le même processus afin de communiquer avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea807-132">The Microsoft 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="ea807-133">Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’y a aucun besoin d’utiliser un serveur de jetons tiers.</span><span class="sxs-lookup"><span data-stu-id="ea807-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="ea807-134">Les produits serveur tels que Lync Server 2013 et Exchange 2013 disposent d’un serveur de jetons intégré qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (par exemple, SharePoint Server) qui prennent en charge l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="ea807-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="ea807-135">Par exemple, Lync Server 2013 peut émettre et signer un jeton de sécurité par lui-même, puis utiliser ce jeton pour communiquer avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ea807-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="ea807-136">Dans un cas comme celui-ci, aucun serveur de jeton tiers n'est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ea807-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="ea807-137">Pour configurer l’authentification de serveur à serveur pour une implémentation locale de Lync Server 2013, vous devez effectuer les deux opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ea807-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="ea807-138">Assigner un certificat à l’émetteur de jetons intégré à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea807-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="ea807-139">Configurez le serveur avec lequel Lync Server 2013 doit communiquer en tant qu’application partenaire.</span><span class="sxs-lookup"><span data-stu-id="ea807-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="ea807-140">Par exemple, si Lync Server 2013 doit communiquer avec Exchange 2013, vous devrez configurer Exchange en tant qu’application partenaire.</span><span class="sxs-lookup"><span data-stu-id="ea807-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ea807-141">Une application partenaire est une application avec laquelle Lync Server 2013 peut directement échanger des jetons de sécurité, sans avoir à passer par un serveur de jetons de sécurité tiers.</span><span class="sxs-lookup"><span data-stu-id="ea807-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="ea807-142">Notez que OAuth est un élément essentiel du produit et qu’il ne peut pas être désactivé ou supprimé.</span><span class="sxs-lookup"><span data-stu-id="ea807-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ea807-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea807-143">See Also</span></span>


[<span data-ttu-id="ea807-144">Affectation d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea807-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="ea807-145">Configuration de Microsoft Lync Server 2013 dans un environnement intersite</span><span class="sxs-lookup"><span data-stu-id="ea807-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

