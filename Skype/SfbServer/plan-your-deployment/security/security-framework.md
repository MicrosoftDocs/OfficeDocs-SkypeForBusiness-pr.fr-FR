---
title: Infrastructure de sécurité pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Skype entreprise Server. Le fait de comprendre le fonctionnement de ces éléments est essentiel pour prendre des décisions éclairées sur la sécurisation de votre déploiement de Skype entreprise Server particulier.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296874"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="0f1c2-104">Infrastructure de sécurité pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f1c2-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="0f1c2-105">Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="0f1c2-106">Le fait de comprendre le fonctionnement de ces éléments est essentiel pour prendre des décisions éclairées sur la sécurisation de votre déploiement de Skype entreprise Server particulier.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="0f1c2-107">Ces éléments sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="0f1c2-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="0f1c2-108">Les services de domaine Active Directory (AD DS) fournissent un référentiel principal approuvé unique pour les comptes d’utilisateurs et les ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="0f1c2-109">RBAC (Contrôle d’accès basé sur un rôle) vous permet de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="0f1c2-110">L’infrastructure à clé publique (PKI, Public Key Infrastructure) utilise des certificats émis par des autorités de certification approuvées afin d’authentifier les serveurs et de garantir l’intégrité des données.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="0f1c2-p103">Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux multimédias point à point sont chiffrés à l’aide du protocole SRTP (protocole de transport sécurisé en temps réel).</span><span class="sxs-lookup"><span data-stu-id="0f1c2-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="0f1c2-113">Protocoles standard d’authentification des utilisateurs, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="0f1c2-114">Windows PowerShell fournit des fonctionnalités de sécurité qui sont activées par défaut, de sorte que les utilisateurs ne peuvent pas facilement exécuter des scripts.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="0f1c2-115">Ces éléments de sécurité fondamentaux collaborent pour définir des utilisateurs, des serveurs, des connexions et des opérations de confiance pour garantir une base sécurisée pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0f1c2-116">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="0f1c2-116">In this section</span></span>

<span data-ttu-id="0f1c2-117">Les rubriques de cette section expliquent comment chacun de ces éléments fondamentaux fonctionne pour renforcer la sécurité de votre infrastructure serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="0f1c2-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="0f1c2-118">Services de domaine Active Directory pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f1c2-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="0f1c2-119">Contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f1c2-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="0f1c2-120">Infrastructure à clé publique pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f1c2-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="0f1c2-121">TLS et MTLS pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f1c2-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="0f1c2-122">Chiffrement pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f1c2-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="0f1c2-123">Authentification des utilisateurs et des clients pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f1c2-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="0f1c2-124">Outils de gestion de Windows PowerShell et de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f1c2-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

