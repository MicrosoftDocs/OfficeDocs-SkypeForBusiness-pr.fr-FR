---
title: 'Lync Server 2013 : renforcement et protection des serveurs et des applications'
description: 'Lync Server 2013 : renforcement et protection des serveurs et des applications.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1205439208dfdadf5396b976d5d4876fb0aa24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567440"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="35220-103">Renforcement et protection des serveurs et des applications pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35220-103">Hardening and protecting servers and applications for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35220-104">_**Dernière modification de la rubrique :** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="35220-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="35220-105">Vous devez renforcer et protéger votre système d’exploitation et vos applications conformément aux meilleures pratiques pour ce composant spécifique.</span><span class="sxs-lookup"><span data-stu-id="35220-105">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="35220-106">Cette section décrit comment renforcer les serveurs d’applications et utiliser la stratégie de groupe pour implémenter les verrouillages de sécurité.</span><span class="sxs-lookup"><span data-stu-id="35220-106">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35220-107">Vous pouvez également renforcer et protéger les bases de données utilisées pour le déploiement de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35220-107">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="35220-108">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hardening-and-protecting-databases.md">la rubrique renforcement et protection des bases de données de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="35220-108">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="35220-109">Sécurisation des serveurs d’applications</span><span class="sxs-lookup"><span data-stu-id="35220-109">Securing Application Servers</span></span>

<span data-ttu-id="35220-110">Pour les serveurs d’applications, le système d’exploitation et l’application doivent être renforcés.</span><span class="sxs-lookup"><span data-stu-id="35220-110">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="35220-111">Par exemple, un ordinateur Windows Server 2008 dédié à l’exécution de Microsoft Internet Security and Acceleration (ISA) Server 2006 doit être renforcé à partir du système d’exploitation et du point de vue de l’application.</span><span class="sxs-lookup"><span data-stu-id="35220-111">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="35220-112">La réduction du nombre de services en cours d’exécution et fournis par le serveur doit être un objectif principal.</span><span class="sxs-lookup"><span data-stu-id="35220-112">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="35220-113">Sécurisation des serveurs virtuels</span><span class="sxs-lookup"><span data-stu-id="35220-113">Securing Virtual Servers</span></span>

<span data-ttu-id="35220-114">Les captures instantanées de serveur virtuel contiennent des copies des disques de données du serveur et contiennent également des dumps de données en mémoire, qui peuvent contenir des données de chiffrement sensibles susceptibles de conduire à des attaques.</span><span class="sxs-lookup"><span data-stu-id="35220-114">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="35220-115">Pour les serveurs de production implémentés à l’aide de la virtualisation, vous devez désactiver toutes les captures instantanées de serveur ou les gérer de manière très contrôlée.</span><span class="sxs-lookup"><span data-stu-id="35220-115">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="35220-116">Pour plus d’informations sur la sécurisation des serveurs virtuels Hyper-V, voir le Guide de sécurité Hyper-V à l’adresse suivante : [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) .</span><span class="sxs-lookup"><span data-stu-id="35220-116">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="35220-117">Stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="35220-117">Group Policy</span></span>

<span data-ttu-id="35220-118">Dans Windows Server 2008 et Windows Server 2008 R2, la stratégie de groupe fournit la gestion de la configuration de bureau basée sur l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="35220-118">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="35220-119">Vous pouvez utiliser la stratégie de groupe pour implémenter les verrouillages de sécurité en définissant les paramètres ordinateur et utilisateur dans un objet de stratégie de groupe (GPO) pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="35220-119">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="35220-120">Stratégies basées sur le registre</span><span class="sxs-lookup"><span data-stu-id="35220-120">Registry-based policies</span></span>

  - <span data-ttu-id="35220-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="35220-121">Security</span></span>

  - <span data-ttu-id="35220-122">Installation de logiciels</span><span class="sxs-lookup"><span data-stu-id="35220-122">Software installation</span></span>

  - <span data-ttu-id="35220-123">Scripts</span><span class="sxs-lookup"><span data-stu-id="35220-123">Scripts</span></span>

  - <span data-ttu-id="35220-124">Redirection de dossiers</span><span class="sxs-lookup"><span data-stu-id="35220-124">Folder redirection</span></span>

  - <span data-ttu-id="35220-125">Services d’installation à distance</span><span class="sxs-lookup"><span data-stu-id="35220-125">Remote installation services</span></span>

<span data-ttu-id="35220-126">Pour fournir une interface utilisateur permettant à l’administrateur de configurer ces paramètres, les modèles d’administration sont fournis avec les versions du système d’exploitation, les versions des service packs et certaines applications, y compris Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35220-126">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="35220-127">Le fichier Communicator. adm est un modèle d’administration fourni avec Lync Server 2013, est installé dans le répertoire% windir% \\ INF \\ et fournit une interface aux paramètres de la stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="35220-127">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="35220-128">Chaque paramètre de Communicator. adm correspond à un paramètre dans le Registre qui affecte le comportement de l’application.</span><span class="sxs-lookup"><span data-stu-id="35220-128">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="35220-129">Les paramètres sont accessibles à partir de GPedit.dll, qui sont disponibles à partir de la console utilisateurs et ordinateurs Active Directory et de la console de gestion des stratégies de groupe (GPMC).</span><span class="sxs-lookup"><span data-stu-id="35220-129">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="35220-130">Paramètres de sécurité de la stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="35220-130">Group Policy Security Settings</span></span>

<span data-ttu-id="35220-131">La stratégie de groupe contient les paramètres de sécurité d’un objet GPO sous Configuration de l’ordinateur/Paramètres Windows/paramètres de sécurité lors de l’accès à partir de GPedit.dll.</span><span class="sxs-lookup"><span data-stu-id="35220-131">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="35220-132">Vous pouvez importer des modèles de sécurité pour configurer les paramètres de sécurité de l’objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="35220-132">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="35220-133">Le Guide de sécurité de Windows Server 2008 à [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) l’adresse et le kit de gestion de la conformité de la sécurité de Windows server 2008 R2, accessible à l’aide de ces [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) modèles, que vous pouvez modifier pour répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="35220-133">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="35220-134">Meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="35220-134">Best Practices</span></span>

  - <span data-ttu-id="35220-135">Renforcer tous les systèmes d’exploitation et applications du serveur.</span><span class="sxs-lookup"><span data-stu-id="35220-135">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="35220-136">Protégez les captures instantanées de serveur et améliorez la sécurité de tous les serveurs virtuels.</span><span class="sxs-lookup"><span data-stu-id="35220-136">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="35220-137">Utiliser la stratégie de groupe pour implémenter les verrouillages de sécurité.</span><span class="sxs-lookup"><span data-stu-id="35220-137">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

