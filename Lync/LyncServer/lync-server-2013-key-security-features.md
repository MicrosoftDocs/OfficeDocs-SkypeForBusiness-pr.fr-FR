---
title: 'Lync Server 2013 : fonctionnalités de sécurité clés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a03a5c312123d714eebe8d49674a19ce712e37bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="88aab-102">Principales fonctionnalités de sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88aab-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88aab-103">_**Dernière modification de la rubrique :** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="88aab-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="88aab-104">Lync Server 2013 comprend plusieurs fonctionnalités de sécurité, notamment l’authentification de serveur à serveur, le contrôle d’accès basé sur un rôle et le stockage centralisé des données de configuration.</span><span class="sxs-lookup"><span data-stu-id="88aab-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="88aab-105">Cet article offre une vue d’ensemble de la sécurité de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aab-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="88aab-106">Principales fonctionnalités de sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88aab-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="88aab-107">La sécurité est un sujet très large.</span><span class="sxs-lookup"><span data-stu-id="88aab-107">Security is a very broad topic.</span></span> <span data-ttu-id="88aab-108">La sécurité atteint toutes les fonctionnalités de Lync Server 2013, ainsi que les bases de données, les services et le matériel qui constituent un écosystème Lync.</span><span class="sxs-lookup"><span data-stu-id="88aab-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="88aab-109">Cet article décrit certaines fonctionnalités de Lync Server 2013, notamment celles conçues pour la sécurité.</span><span class="sxs-lookup"><span data-stu-id="88aab-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="88aab-110">Outils de planification et de conception</span><span class="sxs-lookup"><span data-stu-id="88aab-110">Planning and Design Tools</span></span>

<span data-ttu-id="88aab-111">Lync Server 2013 fournit deux outils pour faciliter la planification et la conception et réduire le risque de configuration inpropre des composants de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88aab-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="88aab-112">L' **outil de planification** de la topologie automatise une grande partie du processus de conception de la topologie.</span><span class="sxs-lookup"><span data-stu-id="88aab-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="88aab-113">Vous pouvez exporter les résultats de l’outil de planification vers le générateur de topologie, qui est l’outil requis pour installer chaque serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aab-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="88aab-114">Le **Générateur de topologies** stocke toutes les informations de configuration dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="88aab-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="88aab-115">Pour plus d’informations sur ces outils, reportez-vous à la rubrique [Planning for Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="88aab-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="88aab-116">Magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="88aab-116">Central Management Store</span></span>

<span data-ttu-id="88aab-117">Dans Lync Server 2013, les données de configuration relatives aux serveurs et services font partie du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="88aab-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="88aab-118">Le magasin central de gestion fournit un stockage robuste et schématisées des données nécessaires pour définir, configurer, maintenir, administrer, décrire et exploiter un déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88aab-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="88aab-119">Il valide également les données afin de garantir la cohérence de la configuration.</span><span class="sxs-lookup"><span data-stu-id="88aab-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="88aab-120">Toutes les modifications apportées à ces données de configuration se produisent dans le magasin central de gestion, ce qui élimine les problèmes de « désynchronisation ».</span><span class="sxs-lookup"><span data-stu-id="88aab-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="88aab-121">Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="88aab-121">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances.</span></span> <span data-ttu-id="88aab-122">La réplication est gérée par un service qui, par défaut, s’exécute sous le contexte du service Réseau, réduisant ainsi les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="88aab-122">Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="88aab-123">Authentification de serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="88aab-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="88aab-124">Dans Lync Server 2013, l’authentification peut être configurée entre les serveurs à l’aide du protocole OAuth (Open Authorization).</span><span class="sxs-lookup"><span data-stu-id="88aab-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="88aab-125">Par exemple, vous pouvez configurer Lync Server 2013 pour l’authentification auprès d’un serveur qui exécute Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aab-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="88aab-126">À l’aide du protocole OAuth, le serveur Lync et le serveur Exchange peuvent se faire confiance les uns des autres.</span><span class="sxs-lookup"><span data-stu-id="88aab-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="88aab-127">Cela permet d’intégrer les produits de manière transparente.</span><span class="sxs-lookup"><span data-stu-id="88aab-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="88aab-128">Pour plus d’informations, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="88aab-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="88aab-129">Interface de gestion basée sur le Web et la gestion basée sur Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88aab-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="88aab-130">Lync Server 2013 fournit une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88aab-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="88aab-131">Elle comprend des applets de commande pour la gestion de la sécurité ; les fonctionnalités de sécurité Windows PowerShell sont activées par défaut, de sorte que les utilisateurs ne puissent pas exécuter de scripts facilement ou inconsciemment.</span><span class="sxs-lookup"><span data-stu-id="88aab-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="88aab-132">Cela signifie que les paramètres par défaut des logiciels sont configurés de façon à optimiser la sécurité et à réduire les itinéraires d’agression.</span><span class="sxs-lookup"><span data-stu-id="88aab-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="88aab-133">Pour plus d’informations sur la prise en charge de la gestion Windows PowerShell dans Lync Server 2013, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="88aab-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="88aab-134">Contrôle d’accès basé sur un rôle</span><span class="sxs-lookup"><span data-stu-id="88aab-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="88aab-135">Microsoft Lync Server 2013 fournit un contrôle d’accès basé sur un rôle (RBAC) pour vous permettre de déléguer des tâches administratives tout en conservant des normes de sécurité élevées.</span><span class="sxs-lookup"><span data-stu-id="88aab-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="88aab-136">Vous pouvez recourir au contrôle d’accès basé sur un rôle pour appliquer le principe du « privilège minimum » selon lequel les utilisateurs reçoivent uniquement les droits d’administration nécessaires à leur travail.</span><span class="sxs-lookup"><span data-stu-id="88aab-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="88aab-137">Lync Server 2013 offre la possibilité de créer un nouveau rôle et de modifier un rôle existant.</span><span class="sxs-lookup"><span data-stu-id="88aab-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="88aab-138">Pour plus d’informations, reportez-vous à la rubrique [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="88aab-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="88aab-139">Traduction d’adresses réseau (NAT)</span><span class="sxs-lookup"><span data-stu-id="88aab-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="88aab-140">Lync Server 2013 ne prend pas en charge l’utilisation de la traduction d’adresses réseau (NAT) sur l’interface interne du serveur Edge, mais il prend en charge la mise en place de l’interface externe du service Edge d’accès, du service Edge de conférence Web et du service Edge A/V derrière un routeur ou un pare</span><span class="sxs-lookup"><span data-stu-id="88aab-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="88aab-141">Plusieurs serveurs Edge derrière un programme d’équilibrage de la charge matérielle ne peuvent pas utiliser le protocole NAT.</span><span class="sxs-lookup"><span data-stu-id="88aab-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="88aab-142">Si plusieurs serveurs Edge utilisent la traduction d’adresses réseau sur leurs interfaces externes, l’équilibrage de charge DNS (Domain Name System) est requis.</span><span class="sxs-lookup"><span data-stu-id="88aab-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="88aab-143">À son tour, l’utilisation de l’équilibrage de charge DNS vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="88aab-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="88aab-144">Pour plus d’informations, consultez la rubrique[planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="88aab-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88aab-145">Si vous vous fédérer avec des entreprises qui ont un déploiement de Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio/vidéo entre votre entreprise et l’entreprise fédérée, les exigences de port seront celles de l’ancienne version des serveurs Edge déployés.</span><span class="sxs-lookup"><span data-stu-id="88aab-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="88aab-146">Par exemple, les plages de ports requises pour ces anciennes versions doivent être ouvertes pour les deux entreprises jusqu’à ce que le partenaire fédéré mette à niveau ses serveurs Edge vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88aab-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="88aab-147">Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration.</span><span class="sxs-lookup"><span data-stu-id="88aab-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="88aab-148">Certificats simplifiés pour les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="88aab-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="88aab-149">L’Assistant Déploiement peut remplir automatiquement les noms du sujet et les autres noms du sujet, réduisant le risque d’inclusion d’entrées inutiles et éventuellement non sécurisées.</span><span class="sxs-lookup"><span data-stu-id="88aab-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="88aab-150">Cycle de vie de développement de la sécurité informatique de confiance (SDL)</span><span class="sxs-lookup"><span data-stu-id="88aab-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="88aab-151">Lync Server 2013 est conçu et développé conformément au cycle de vie de développement de la sécurité Microsoft Trustworthy Computing (SDL), <https://go.microsoft.com/fwlink/?linkid=68761>qui est décrit à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="88aab-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <https://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="88aab-152">**Fiabilité par conception**   la première étape de la création d’un système de communications unifiées plus sécurisé consistait à concevoir des modèles de menaces et à tester chaque fonctionnalité au fur et à mesure de leur conception.</span><span class="sxs-lookup"><span data-stu-id="88aab-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="88aab-153">De plus, Microsoft effectue des tests en dehors du comportement conçu afin de trouver des failles de sécurité résultant d’un comportement inattendu du produit.</span><span class="sxs-lookup"><span data-stu-id="88aab-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="88aab-154">Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage.</span><span class="sxs-lookup"><span data-stu-id="88aab-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="88aab-155">Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final.</span><span class="sxs-lookup"><span data-stu-id="88aab-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="88aab-156">Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues.</span><span class="sxs-lookup"><span data-stu-id="88aab-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="88aab-157">Aucun système ne saurait garantir une sécurité à toute épreuve.</span><span class="sxs-lookup"><span data-stu-id="88aab-157">No system can guarantee complete security.</span></span> <span data-ttu-id="88aab-158">Toutefois, étant donné que le développement de produits a adopté des principes de conception sécurisée dès le départ, Lync Server 2013 incorpore des technologies de sécurité standard en tant que partie fondamentale de son architecture.</span><span class="sxs-lookup"><span data-stu-id="88aab-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="88aab-159">**Digne de confiance**par défaut, les communications réseau dans Lync Server 2013 sont chiffrées.   </span><span class="sxs-lookup"><span data-stu-id="88aab-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="88aab-160">Étant donné que tous les serveurs utilisent des certificats et l’authentification Kerberos, TLS, le protocole SRTP (Secure Real-Time Transport Protocol) et d’autres techniques de chiffrement standard, y compris le chiffrement AES (Advanced Encryption Standard) 128 bits, pratiquement tous les Lync Les données du serveur sont protégées sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="88aab-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="88aab-161">De plus, le contrôle d’accès basé sur les rôles permet de déployer des serveurs exécutant Lync Server 2013 de sorte que chaque rôle serveur n’exécute que les services, et ne dispose que des autorisations liées à ces services, qui sont appropriées pour le rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="88aab-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="88aab-162">**Confiance par le déploiement**   toute la documentation Lync Server 2013 inclut les meilleures pratiques et recommandations pour vous aider à déterminer et à configurer les niveaux de sécurité optimaux pour votre déploiement et à évaluer les risques de sécurité liés à l’activation d’options autres que celles par défaut.</span><span class="sxs-lookup"><span data-stu-id="88aab-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

