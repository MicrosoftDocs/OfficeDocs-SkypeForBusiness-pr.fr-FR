---
title: 'Lync Server 2013 : renforcement et protection des serveurs et des applications'
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
ms.openlocfilehash: 42b8b9d3fc21c590bda12841cb6002987d4c0650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="e40ae-102">Renforcement et protection des serveurs et des applications pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e40ae-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e40ae-103">_**Dernière modification de la rubrique :** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="e40ae-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="e40ae-104">Vous devez renforcer et protéger votre système d’exploitation et vos applications conformément aux meilleures pratiques pour ce composant spécifique.</span><span class="sxs-lookup"><span data-stu-id="e40ae-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="e40ae-105">Cette section explique comment renforcer les serveurs d’applications et utiliser une stratégie de groupe pour implémenter les verrouillages de sécurité.</span><span class="sxs-lookup"><span data-stu-id="e40ae-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e40ae-106">Vous pouvez également renforcer et protéger les bases de données utilisées pour le déploiement de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e40ae-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="e40ae-107">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hardening-and-protecting-databases.md">la rubrique renforcement et protection des bases de données de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e40ae-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="e40ae-108">Sécurisation des serveurs d’applications</span><span class="sxs-lookup"><span data-stu-id="e40ae-108">Securing Application Servers</span></span>

<span data-ttu-id="e40ae-109">Pour les serveurs d’applications, le système d’exploitation et l’application doivent être renforcés.</span><span class="sxs-lookup"><span data-stu-id="e40ae-109">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="e40ae-110">Par exemple, un ordinateur Windows Server 2008 destiné à exécuter Microsoft Internet Security and Acceleration (ISA) Server 2006 doit être renforcé à partir du système d’exploitation et du point de vue de l’application.</span><span class="sxs-lookup"><span data-stu-id="e40ae-110">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="e40ae-111">Il est préférable de réduire le nombre de services en cours d’exécution et fournis par le serveur.</span><span class="sxs-lookup"><span data-stu-id="e40ae-111">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="e40ae-112">Sécurisation des serveurs virtuels</span><span class="sxs-lookup"><span data-stu-id="e40ae-112">Securing Virtual Servers</span></span>

<span data-ttu-id="e40ae-113">Les instantanés du serveur virtuel contiennent des copies des disques de données du serveur et contiennent également des vidages de données en mémoire, qui peuvent contenir des données de chiffrement sensibles susceptibles de provoquer des attaques.</span><span class="sxs-lookup"><span data-stu-id="e40ae-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="e40ae-114">Pour les serveurs de production implémentés à l’aide de la virtualisation, il est recommandé de désactiver toutes les captures d’instantanés serveur ou de les gérer de manière très contrôlée.</span><span class="sxs-lookup"><span data-stu-id="e40ae-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="e40ae-115">Pour plus d’informations sur la sécurisation des serveurs virtuels Hyper-V, voir le guide sur [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)la sécurité Hyper-v sur le :.</span><span class="sxs-lookup"><span data-stu-id="e40ae-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="e40ae-116">Stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="e40ae-116">Group Policy</span></span>

<span data-ttu-id="e40ae-117">Dans Windows Server 2008 et Windows Server 2008 R2, la stratégie de groupe fournit la gestion de la configuration de bureau basée sur un annuaire.</span><span class="sxs-lookup"><span data-stu-id="e40ae-117">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="e40ae-118">Vous pouvez utiliser une stratégie de groupe pour implémenter les verrouillages de sécurité en définissant des paramètres d’ordinateur et d’utilisateur au sein d’un objet de stratégie de groupe pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e40ae-118">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="e40ae-119">Stratégies basées sur le registre</span><span class="sxs-lookup"><span data-stu-id="e40ae-119">Registry-based policies</span></span>

  - <span data-ttu-id="e40ae-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e40ae-120">Security</span></span>

  - <span data-ttu-id="e40ae-121">Installation de logiciels</span><span class="sxs-lookup"><span data-stu-id="e40ae-121">Software installation</span></span>

  - <span data-ttu-id="e40ae-122">Scripts</span><span class="sxs-lookup"><span data-stu-id="e40ae-122">Scripts</span></span>

  - <span data-ttu-id="e40ae-123">Redirection de dossiers</span><span class="sxs-lookup"><span data-stu-id="e40ae-123">Folder redirection</span></span>

  - <span data-ttu-id="e40ae-124">Services d’installation à distance</span><span class="sxs-lookup"><span data-stu-id="e40ae-124">Remote installation services</span></span>

<span data-ttu-id="e40ae-125">Pour fournir une interface utilisateur permettant à l’administrateur de configurer ces paramètres, les modèles d’administration sont livrés avec les versions de système d’exploitation, les versions de Service Pack et certaines applications, y compris Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e40ae-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="e40ae-126">Le fichier Communicator. adm est un modèle d’administration fourni avec Lync Server 2013, qui est installé sur le répertoire% windir\\%\\ INF et fournit une interface aux paramètres de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="e40ae-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="e40ae-127">Chaque paramètre dans Communicator. adm correspond à un paramètre du Registre affectant le comportement de l’application.</span><span class="sxs-lookup"><span data-stu-id="e40ae-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="e40ae-128">Il est possible d’accéder aux paramètres à partir de GPedit. dll, qui est disponible dans la console utilisateurs et ordinateurs Active Directory et la console de gestion des stratégies de groupe (GPMC).</span><span class="sxs-lookup"><span data-stu-id="e40ae-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="e40ae-129">Paramètres de sécurité de stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="e40ae-129">Group Policy Security Settings</span></span>

<span data-ttu-id="e40ae-130">La stratégie de groupe contient les paramètres de sécurité d’un objet de stratégie de groupe sous Configuration ordinateur/Paramètres Windows/paramètres de sécurité lorsqu’il est consulté à partir de GPedit. dll.</span><span class="sxs-lookup"><span data-stu-id="e40ae-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="e40ae-131">Vous pouvez importer des modèles de sécurité pour configurer les paramètres de sécurité de l’objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="e40ae-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="e40ae-132">Le guide sur la sécurité de Windows [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) Server 2008 de et le kit de gestion de la sécurité [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) Windows Server 2008 R2 Security Compliance pour contiennent un certain nombre d’exemples de modèles que vous pouvez modifier en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="e40ae-132">The Windows Server 2008 Security Guide at [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="e40ae-133">Meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="e40ae-133">Best Practices</span></span>

  - <span data-ttu-id="e40ae-134">Renforcez tous les systèmes d’exploitation et applications du serveur.</span><span class="sxs-lookup"><span data-stu-id="e40ae-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="e40ae-135">Protéger les clichés du serveur et renforcer la sécurité de tous les serveurs virtuels.</span><span class="sxs-lookup"><span data-stu-id="e40ae-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="e40ae-136">Utiliser une stratégie de groupe pour implémenter les verrouillages de sécurité.</span><span class="sxs-lookup"><span data-stu-id="e40ae-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

