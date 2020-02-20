---
title: 'Lync Server 2013 : infrastructure de sécurité pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 472e15d2206e787abb571885f0155bb0169f7234
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="0313e-102">Infrastructure de sécurité pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0313e-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0313e-103">_**Dernière modification de la rubrique :** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="0313e-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="0313e-104">Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité pour Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0313e-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="0313e-105">Il est essentiel de comprendre comment ces éléments interagissent pour prendre des décisions éclairées concernant la sécurisation de votre déploiement de Lync Server 2013 particulier.</span><span class="sxs-lookup"><span data-stu-id="0313e-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="0313e-106">Ces éléments sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="0313e-106">These elements are as follows:</span></span>

  - <span data-ttu-id="0313e-107">Les services de domaine Active Directory offrent un référentiel centralisé, unique et fiable aux comptes d’utilisateurs et aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="0313e-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="0313e-108">Le contrôle d’accès basé sur un rôle (RBAC) vous permet de déléguer des tâches administratives tout en conservant des normes de sécurité élevées.</span><span class="sxs-lookup"><span data-stu-id="0313e-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="0313e-109">L’infrastructure à clé publique (PKI) utilise des certificats émis par des autorités de certification approuvées pour authentifier les serveurs et garantir l’intégrité des données.</span><span class="sxs-lookup"><span data-stu-id="0313e-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="0313e-p102">Les protocoles TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et Mutual TLS (MTLS) permettent l’authentification des systèmes d’extrémité et le chiffrement des communications par messagerie instantanée. Les flux audio, vidéo et de partage d’application point à point sont chiffrés à l’aide du protocole SRTP (Secure Real Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="0313e-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="0313e-112">Des protocoles standard sont utilisés pour l’authentification des utilisateurs, lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="0313e-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="0313e-113">Windows PowerShell propose des fonctionnalités de sécurité activées par défaut afin que les utilisateurs ne puissent pas exécuter des scripts facilement ou sans le savoir.</span><span class="sxs-lookup"><span data-stu-id="0313e-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="0313e-114">Ces éléments de sécurité fondamentaux fonctionnent ensemble pour définir des utilisateurs, des serveurs, des connexions et des opérations approuvés afin de garantir une base sécurisée pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0313e-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0313e-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0313e-115">In This Section</span></span>

<span data-ttu-id="0313e-116">Les rubriques de cette section décrivent le fonctionnement de chacun de ces éléments fondamentaux afin d’améliorer la sécurité de votre infrastructure Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0313e-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="0313e-117">Services de domaine Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0313e-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="0313e-118">Contrôle d’accès basé sur un rôle (RBAC) pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0313e-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="0313e-119">Infrastructure de clé publique pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0313e-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="0313e-120">TLS et MTLS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0313e-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="0313e-121">Chiffrement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0313e-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="0313e-122">Authentification utilisateur et client pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0313e-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="0313e-123">Outils de gestion Windows PowerShell et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0313e-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

