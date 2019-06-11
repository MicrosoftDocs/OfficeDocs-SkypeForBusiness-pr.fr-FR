---
title: 'Lync Server 2013: infrastructure de sécurité pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="49a80-102">Infrastructure de sécurité pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49a80-103">_**Dernière modification de la rubrique:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="49a80-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="49a80-104">Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49a80-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="49a80-105">Il est essentiel de comprendre la façon dont ces éléments collaborent pour prendre des décisions éclairées sur la sécurisation de votre déploiement de Lync Server 2013 particulier.</span><span class="sxs-lookup"><span data-stu-id="49a80-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="49a80-106">Ces éléments sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="49a80-106">These elements are as follows:</span></span>

  - <span data-ttu-id="49a80-107">Les services de domaine Active Directory (AD DS) fournissent un référentiel principal approuvé unique pour les comptes d’utilisateurs et les ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="49a80-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="49a80-108">RBAC (Contrôle d’accès basé sur un rôle) vous permet de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="49a80-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="49a80-109">L’infrastructure à clé publique (PKI, Public Key Infrastructure) utilise des certificats émis par des autorités de certification approuvées afin d’authentifier les serveurs et de garantir l’intégrité des données.</span><span class="sxs-lookup"><span data-stu-id="49a80-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="49a80-p102">Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux multimédias point à point sont chiffrés à l’aide du protocole SRTP (protocole de transport sécurisé en temps réel).</span><span class="sxs-lookup"><span data-stu-id="49a80-p102">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="49a80-112">Protocoles standard d’authentification des utilisateurs, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="49a80-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="49a80-113">Windows PowerShell fournit des fonctionnalités de sécurité qui sont activées par défaut, de sorte que les utilisateurs ne peuvent pas facilement exécuter des scripts.</span><span class="sxs-lookup"><span data-stu-id="49a80-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="49a80-114">Ces éléments de sécurité fondamentaux collaborent pour définir des utilisateurs, des serveurs, des connexions et des opérations de confiance pour garantir une base sécurisée pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49a80-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="49a80-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="49a80-115">In This Section</span></span>

<span data-ttu-id="49a80-116">Les rubriques de cette section expliquent comment chacun de ces éléments fondamentaux fonctionne pour renforcer la sécurité de votre infrastructure serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="49a80-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="49a80-117">Services de domaine Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="49a80-118">Contrôle d’accès basé sur les rôles (RBAC) pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="49a80-119">Infrastructure à clé publique pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="49a80-120">TLS et MTLS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="49a80-121">Chiffrement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="49a80-122">Authentification utilisateur et client pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="49a80-123">Outils de gestion de Windows PowerShell et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a80-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

