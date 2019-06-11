---
title: 'Lync Server 2013: principales fonctionnalités de sécurité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="53971-102">Principales fonctionnalités de sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53971-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53971-103">_**Dernière modification de la rubrique:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="53971-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="53971-104">Lync Server 2013 inclut plusieurs fonctionnalités de sécurité, notamment l’authentification de serveur à serveur, le contrôle d’accès basé sur un rôle et le stockage centralisé des données de configuration.</span><span class="sxs-lookup"><span data-stu-id="53971-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="53971-105">Cet article fournit une vue d’ensemble de haut niveau de la sécurité de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53971-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="53971-106">Principales fonctionnalités de sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53971-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="53971-107">La sécurité est un sujet très large.</span><span class="sxs-lookup"><span data-stu-id="53971-107">Security is a very broad topic.</span></span> <span data-ttu-id="53971-108">La sécurité s’étend à toutes les fonctionnalités de Lync Server 2013 ainsi qu’aux bases de données, services et matériels qui constituent un écosystème Lync.</span><span class="sxs-lookup"><span data-stu-id="53971-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="53971-109">Cet article présente certaines des fonctionnalités de Lync Server 2013 en particulier qui sont conçues pour la sécurité.</span><span class="sxs-lookup"><span data-stu-id="53971-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="53971-110">Outils de planification et de conception</span><span class="sxs-lookup"><span data-stu-id="53971-110">Planning and Design Tools</span></span>

<span data-ttu-id="53971-111">Lync Server 2013 fournit deux outils pour faciliter la planification et la conception, et limiter les risques de configuration des composants serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="53971-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="53971-112">L' **outil de planification topologique** automatise une grande partie du processus de conception topologique.</span><span class="sxs-lookup"><span data-stu-id="53971-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="53971-113">Vous pouvez exporter les résultats de l’outil de planification au générateur de topologie, qui est l’outil requis pour installer chaque serveur exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53971-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="53971-114">**Le générateur de topologie** stocke toutes les informations de configuration dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="53971-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="53971-115">Pour plus d’informations sur ces outils, voir [planification de Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="53971-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="53971-116">Magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="53971-116">Central Management Store</span></span>

<span data-ttu-id="53971-117">Dans Lync Server 2013, les données de configuration relatives aux serveurs et services font partie du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="53971-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="53971-118">Le centre de gestion central fournit un stockage puissant et schematized des données nécessaires pour définir, configurer, gérer, gérer, décrire et utiliser un déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53971-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="53971-119">Il valide également les données afin de garantir la cohérence de la configuration.</span><span class="sxs-lookup"><span data-stu-id="53971-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="53971-120">Toutes les modifications apportées aux données de configuration ont lieu dans le magasin central de gestion, ce qui élimine les problèmes de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="53971-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="53971-p104">Les copies en lecture seule des données sont répliquées sur tous les serveurs au sein de la topologie, y compris les serveurs Edge et les serveurs Survivable Branch Appliance. La réplication est gérée par un service exécuté par défaut dans le contexte du service réseau, ce qui limite les droits et autorisations à ceux d’un simple utilisateur sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="53971-p104">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances. Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="53971-123">Authentification serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="53971-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="53971-124">Dans Lync Server 2013, il est possible de configurer l’authentification entre les serveurs à l’aide du protocole d’autorisation Open (OAuth).</span><span class="sxs-lookup"><span data-stu-id="53971-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="53971-125">Par exemple, vous pouvez configurer Lync Server 2013 pour s’authentifier auprès d’un serveur exécutant Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53971-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="53971-126">À l’aide du protocole OAuth, le serveur Lync et le serveur Exchange peuvent être approuvés.</span><span class="sxs-lookup"><span data-stu-id="53971-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="53971-127">Cela permet d’intégrer les produits de façon transparente.</span><span class="sxs-lookup"><span data-stu-id="53971-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="53971-128">Pour plus d’informations, reportez-vous à [gestion des applications d’authentification de serveur à serveur (OAuth) et de partenaire dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="53971-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="53971-129">Interface de gestion Windows PowerShell et web</span><span class="sxs-lookup"><span data-stu-id="53971-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="53971-130">Lync Server 2013 fournit une interface de gestion puissante, basée sur l’interface de ligne de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53971-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="53971-131">Il inclut des cmdlets de gestion de la sécurité et les fonctionnalités de sécurité de Windows PowerShell sont activées par défaut, de sorte que les utilisateurs ne peuvent pas facilement exécuter des scripts.</span><span class="sxs-lookup"><span data-stu-id="53971-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="53971-132">Cela signifie que les logiciels par défaut sont configurés pour renforcer la sécurité et réduire les possibilités d’attaque.</span><span class="sxs-lookup"><span data-stu-id="53971-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="53971-133">Pour plus d’informations sur la prise en charge de Windows PowerShell Management dans Lync Server 2013, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="53971-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="53971-134">Contrôle d’accès basé sur un rôle (RBAC)</span><span class="sxs-lookup"><span data-stu-id="53971-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="53971-135">Microsoft Lync Server 2013 fournit un contrôle d’accès basé sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité des normes.</span><span class="sxs-lookup"><span data-stu-id="53971-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="53971-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span><span class="sxs-lookup"><span data-stu-id="53971-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="53971-137">Lync Server 2013 introduit la possibilité de créer un nouveau rôle et de modifier un rôle existant.</span><span class="sxs-lookup"><span data-stu-id="53971-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="53971-138">Pour plus d’informations, reportez-vous à [planification du contrôle d’accès basé sur les rôles dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="53971-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="53971-139">Traduction d’adresses réseau (NAT)</span><span class="sxs-lookup"><span data-stu-id="53971-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="53971-140">Lync Server 2013 ne prend pas en charge l’utilisation de la traduction d’adresses réseau (NAT) sur l’interface interne du serveur Edge, mais il prend en charge le placement de l’interface externe du service Edge d’accès, du service Edge de conférence Web et du service Edge A/V derrière un routeur ou pare-feu qui exécute la traduction d’adresses réseau (NAT) pour les topologies de serveur de périphérie unique et à l’échelle.</span><span class="sxs-lookup"><span data-stu-id="53971-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="53971-141">S’il y a plusieurs serveurs Edge utilisant un programme d’équilibrage de la charge matérielle, ils ne peuvent pas utiliser la traduction d’adresses réseau.</span><span class="sxs-lookup"><span data-stu-id="53971-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="53971-142">Si plusieurs serveurs Edge utilisent la traduction d’adresses réseau sur leurs interfaces externes, l’équilibrage de la charge DNS (Domain Name System) est requise.</span><span class="sxs-lookup"><span data-stu-id="53971-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="53971-143">L’utilisation de l’équilibrage de la charge DNS vous permet de réduire le nombre d’adresses IP publiques par serveur Edge dans un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="53971-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="53971-144">Pour plus d’informations, reportez-vous à la[planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="53971-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53971-145">Si vous vous fédérez avec des entreprises qui ont un déploiement de Microsoft Office Communications Server 2007 et que vous devez utiliser l’audio et la vidéo entre votre entreprise et une entreprise fédérée, les ports utilisés seront ceux de l’ancienne version des serveurs Edge déployés.</span><span class="sxs-lookup"><span data-stu-id="53971-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="53971-146">Par exemple, les plages de ports requises pour ces versions antérieures doivent être ouvertes pour les deux entreprises tant que le partenaire fédéré a mis à niveau ses serveurs Edge vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53971-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="53971-147">Les exigences relatives aux ports peuvent alors être réévaluées et réduites, conformément à la nouvelle configuration.</span><span class="sxs-lookup"><span data-stu-id="53971-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="53971-148">Certificats simplifiés pour les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="53971-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="53971-149">L’Assistant Déploiement peut renseigner automatiquement les noms du sujet et les autres noms du sujet, et minimiser ainsi la possibilité d’inclure des entrées inutiles et éventuellement non sécurisées.</span><span class="sxs-lookup"><span data-stu-id="53971-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="53971-150">Cycle de développement d’une sécurité informatique fiable</span><span class="sxs-lookup"><span data-stu-id="53971-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="53971-151">Lync Server 2013 est conçu et développé conformément au cycle de vie de développement de la sécurité Microsoft Trustworthy Computing (SDL), <http://go.microsoft.com/fwlink/?linkid=68761>qui est décrit à la section.</span><span class="sxs-lookup"><span data-stu-id="53971-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <http://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="53971-152">**Digne de confiance en concevant**   la première étape de la création d’un système de communication unifiée plus sécurisé consistait à concevoir des modèles de menaces et à tester chaque fonctionnalité au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="53971-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="53971-153">De plus, Microsoft effectue des tests sur des comportements anormaux afin de détecter les failles de sécurité résultant d’un comportement inattendu du produit.</span><span class="sxs-lookup"><span data-stu-id="53971-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="53971-154">Plusieurs améliorations liées à la sécurité ont été intégrées dans le processus et les pratiques de codage.</span><span class="sxs-lookup"><span data-stu-id="53971-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="53971-155">Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final.</span><span class="sxs-lookup"><span data-stu-id="53971-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="53971-156">Bien entendu, il est impossible de concevoir un produit capable de contrer toutes les menaces de sécurité encore inconnues.</span><span class="sxs-lookup"><span data-stu-id="53971-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="53971-157">Aucun système ne saurait garantir une sécurité à toute épreuve.</span><span class="sxs-lookup"><span data-stu-id="53971-157">No system can guarantee complete security.</span></span> <span data-ttu-id="53971-158">Toutefois, étant donné que le développement de produits a adopté des principes de conception sécurisés depuis le début, Lync Server 2013 inclut les technologies de sécurité standard de l’industrie comme partie fondamentales de son architecture.</span><span class="sxs-lookup"><span data-stu-id="53971-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="53971-159">**Digne de confiance**par défaut, les communications réseau dans Lync Server 2013 sont chiffrées.   </span><span class="sxs-lookup"><span data-stu-id="53971-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="53971-160">Dans la mesure où tous les serveurs utilisent des certificats et l’authentification Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) et d’autres techniques de cryptage standard de l’industrie, y compris le chiffrement AES (Advanced Encryption Standard) 128 bits, tout en Lync Les données du serveur sont protégées sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="53971-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="53971-161">De plus, le contrôle d’accès basé sur les rôles permet de déployer des serveurs exécutant Lync Server 2013 de sorte que chaque rôle de serveur exécute uniquement les services et que seules les autorisations associées à ces services soient appropriées pour le rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="53971-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="53971-162">**Fiable par le déploiement**   toutes les informations de la documentation Lync Server 2013 incluent des pratiques recommandées et des recommandations pour vous aider à déterminer et à configurer les niveaux de sécurité optimaux pour votre déploiement et évaluer les risques liés à l’activation de la sécurité par défaut. Options.</span><span class="sxs-lookup"><span data-stu-id="53971-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

