---
title: 'Lync Server 2013 : Préparation des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="def27-102">Préparation des services de domaine Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="def27-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="def27-103">_**Dernière modification de la rubrique:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="def27-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="def27-104">Dans Lync Server 2013, vous pouvez utiliser l’Assistant Déploiement de Lync Server pour préparer les services de domaine Active Directory, ou vous pouvez utiliser les applets de cmdlet Lync Server Management Shell directement.</span><span class="sxs-lookup"><span data-stu-id="def27-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="def27-105">Vous pouvez également utiliser l’outil de ligne de commande LDIFDE. exe directement sur vos contrôleurs de domaine, tel que décrit plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="def27-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="def27-106">L’Assistant Déploiement de Lync Server vous guide à travers chaque tâche de préparation d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="def27-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="def27-107">L’Assistant Déploiement exécute les applets de cmdlet Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="def27-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="def27-108">Cet outil est utile pour les environnements dotés d’une topologie de domaine unique et de forêt unique ou d’une autre topologie similaire.</span><span class="sxs-lookup"><span data-stu-id="def27-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="def27-109">Vous pouvez déployer Lync Server dans une forêt ou un domaine où les contrôleurs de domaine exécutent des versions 32 bits de certains systèmes d’exploitation (pour plus d’informations, voir <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013</A>).</span><span class="sxs-lookup"><span data-stu-id="def27-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="def27-110">Toutefois, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour exécuter une préparation de schéma, de forêt et de domaine dans ces environnements, car l’Assistant Déploiement et les fichiers de prise en charge sont uniquement de la 64.</span><span class="sxs-lookup"><span data-stu-id="def27-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="def27-111">Au lieu de cela, vous pouvez utiliser Ldifde. exe et les fichiers. ldf associés sur un contrôleur de domaine 32 bits pour préparer le schéma, la forêt et le domaine.</span><span class="sxs-lookup"><span data-stu-id="def27-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="def27-112">Voir la section «utilisation des cmdlets et LDIFDE. exe» plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="def27-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="def27-113">Vous pouvez utiliser les applets de commande Lync Server Management Shell pour effectuer des tâches à distance ou pour des environnements plus complexes.</span><span class="sxs-lookup"><span data-stu-id="def27-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="def27-114">Conditions préalables à la préparation d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="def27-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="def27-115">Vous devez exécuter les étapes de préparation d’Active Directory sur un ordinateur exécutant Windows Server 2012, Windows Server 2012 R2 ou Windows Server 2008 R2 avec SP1 (64-bit).</span><span class="sxs-lookup"><span data-stu-id="def27-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="def27-116">La préparation d’Active Directory nécessite Lync Server Management Shell et OCSCore.</span><span class="sxs-lookup"><span data-stu-id="def27-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="def27-117">Les composants suivants sont nécessaires à l’exécution des tâches de préparation d’Active Directory:</span><span class="sxs-lookup"><span data-stu-id="def27-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="def27-118">Composants principaux de Lync Server (OCScore. msi)</span><span class="sxs-lookup"><span data-stu-id="def27-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="def27-119">Si vous envisagez d’utiliser Lync Server Management Shell pour la préparation d’Active Directory, vous devez d’abord exécuter l’Assistant Déploiement de Lync Server pour installer les composants principaux.</span><span class="sxs-lookup"><span data-stu-id="def27-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="def27-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="def27-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="def27-121">Pour Windows Server 2012 et Windows Server 2012 R2, vous installez et activez .NET Framework 4,5 à l’aide du gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="def27-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="def27-122">Pour plus d’informations, 4,5 consultez la <A href="lync-server-2013-additional-software-requirements.md">configuration logicielle requise pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="def27-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="def27-123">Pour Windows Server&nbsp;2008&nbsp;R2, téléchargez et installez <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.NET Framework 4,5</A> à partir du site Web Microsoft.</span><span class="sxs-lookup"><span data-stu-id="def27-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="def27-124">Outils d’administration de serveur distant (RSAT)</span><span class="sxs-lookup"><span data-stu-id="def27-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="def27-125">Certains outils de RSAT sont requis si vous exécutez les étapes de préparation d’Active Directory sur un serveur membre plutôt que sur un contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="def27-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="def27-126">Installez les composants logiciels enfichables et les outils de ligne de commande AD DS et le module Active Directory pour Windows PowerShell à partir du nœud AD DS et des outils AD LDS dans le gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="def27-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="def27-127">Microsoft Visual C++ 11 redistribuable</span><span class="sxs-lookup"><span data-stu-id="def27-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="def27-128">Le programme d’installation vous invite à installer cette configuration requise s’il n’est pas déjà installé sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="def27-128">Setup prompts you to install this prerequisite if it is not already installed on the computer.</span></span> <span data-ttu-id="def27-129">Le package est fourni pour vous, et vous n’avez pas besoin de l’acquérir séparément.</span><span class="sxs-lookup"><span data-stu-id="def27-129">The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="def27-130">Windows PowerShell 3,0 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="def27-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="def27-131">Pour Windows Server 2012 et Windows Server 2012 R2, Windows PowerShell 3,0 doit être inclus avec votre installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="def27-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="def27-132">Pour Windows Server 2008 R2, vous devez installer ou effectuer une mise à niveau vers Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="def27-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="def27-133">Pour plus d’informations, voir [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="def27-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="def27-134">Droits d’administrateur et rôles</span><span class="sxs-lookup"><span data-stu-id="def27-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="def27-135">Le tableau suivant répertorie les droits d’administration et les rôles requis pour chaque tâche de préparation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="def27-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="def27-136">Droits d’utilisateur requis pour la préparation d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="def27-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="def27-137">Intérieur</span><span class="sxs-lookup"><span data-stu-id="def27-137">Procedure</span></span></th>
<th><span data-ttu-id="def27-138">Droits ou rôles</span><span class="sxs-lookup"><span data-stu-id="def27-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="def27-139">Préparation d’un schéma</span><span class="sxs-lookup"><span data-stu-id="def27-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="def27-140">Membre du groupe administrateurs de schéma pour le domaine racine de la forêt et les droits d’administrateur sur le maître de schéma</span><span class="sxs-lookup"><span data-stu-id="def27-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="def27-141">Préparation d’une forêt</span><span class="sxs-lookup"><span data-stu-id="def27-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="def27-142">Membre du groupe administrateurs d’entreprise pour la forêt</span><span class="sxs-lookup"><span data-stu-id="def27-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="def27-143">Préparation d’un domaine</span><span class="sxs-lookup"><span data-stu-id="def27-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="def27-144">Membre du groupe administrateurs d’entreprise ou administrateurs de domaine pour le domaine spécifié</span><span class="sxs-lookup"><span data-stu-id="def27-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="def27-145">Cmdlets de préparation Active Directory</span><span class="sxs-lookup"><span data-stu-id="def27-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="def27-146">Le tableau suivant compare les applets de commande Lync Server Management Shell utilisées pour préparer AD DS aux commandes LcsCmd utilisées pour préparer AD DS dans Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="def27-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="def27-147">Cmdlets par rapport à LcsCmd</span><span class="sxs-lookup"><span data-stu-id="def27-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="def27-148">Applets</span><span class="sxs-lookup"><span data-stu-id="def27-148">Cmdlets</span></span></th>
<th><span data-ttu-id="def27-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="def27-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="def27-150">Install-CSAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="def27-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="def27-151">LcsCmd/Forest/action: SchemaPrep/SchemaType: Server</span><span class="sxs-lookup"><span data-stu-id="def27-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="def27-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="def27-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="def27-153">LcsCmd/Forest/action: CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="def27-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="def27-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="def27-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="def27-155">LcsCmd/Forest/action: ForestPrep</span><span class="sxs-lookup"><span data-stu-id="def27-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="def27-156">Disable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="def27-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="def27-157">LcsCmd/Forest/action: ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="def27-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="def27-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="def27-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="def27-159">LcsCmd/Forest/action: CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="def27-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="def27-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="def27-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="def27-161">LcsCmd/Domain/action: DomainPrep</span><span class="sxs-lookup"><span data-stu-id="def27-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="def27-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="def27-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="def27-163">LcsCmd/Domain/action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="def27-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="def27-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="def27-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="def27-165">LcsCmd/Domain/action: CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="def27-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="def27-166">Configuration requise pour Active Directory</span><span class="sxs-lookup"><span data-stu-id="def27-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="def27-167">Si l’héritage des autorisations est désactivé ou que les autorisations de l’utilisateur authentifié doivent être désactivées au sein de votre organisation, vous devez effectuer des étapes supplémentaires lors de la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="def27-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="def27-168">Pour plus d’informations, reportez-vous à [la rubrique préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="def27-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="def27-169">Autorisations de conteneur personnalisé</span><span class="sxs-lookup"><span data-stu-id="def27-169">Custom Container Permissions</span></span>

<span data-ttu-id="def27-170">Si votre organisation utilise des conteneurs personnalisés au lieu de trois conteneurs intégrés (utilisateurs, ordinateurs et contrôleurs de domaine), vous devez accorder l’accès en lecture aux conteneurs personnalisés pour le groupe utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="def27-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="def27-171">L’accès en lecture aux conteneurs est requis pour la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="def27-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="def27-172">Pour plus d’informations, consultez [préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md).</span><span class="sxs-lookup"><span data-stu-id="def27-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="def27-173">Utilisation des cmdlets et LDIFDE. exe</span><span class="sxs-lookup"><span data-stu-id="def27-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="def27-174">Dans l’étape **préparer le schéma** de l’Assistant Déploiement de Lync Server et de l’applet de commandes **installation-CsAdServerSchema** , étendez le schéma Active Directory sur les contrôleurs de domaine exécutant un système d’exploitation 64 bits.</span><span class="sxs-lookup"><span data-stu-id="def27-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="def27-175">Si vous devez prolonger le schéma Active Directory sur un contrôleur de domaine exécutant un système d’exploitation 32 bits, vous pouvez exécuter l’applet de commande **install-CsAdServerSchema** à distance à partir d’un serveur membre (approche recommandée).</span><span class="sxs-lookup"><span data-stu-id="def27-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="def27-176">Toutefois, si vous devez exécuter une préparation de schéma directement sur le contrôleur de domaine, vous pouvez utiliser l’outil LDIFDE. exe pour importer les fichiers de schéma.</span><span class="sxs-lookup"><span data-stu-id="def27-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="def27-177">L’outil LDIFDE. exe est fourni avec la plupart des versions du système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="def27-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="def27-178">Si vous utilisez LDIFDE. exe pour importer les fichiers de schéma, vous devez importer les quatre fichiers, que vous utilisiez la migration à partir d’une version précédente ou que vous effectuiez une nouvelle installation.</span><span class="sxs-lookup"><span data-stu-id="def27-178">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation.</span></span> <span data-ttu-id="def27-179">Vous devez les importer dans l’ordre suivant:</span><span class="sxs-lookup"><span data-stu-id="def27-179">You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="def27-180">ExternalSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="def27-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="def27-181">ServerSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="def27-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="def27-182">BackCompatSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="def27-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="def27-183">VersionSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="def27-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="def27-184">Les quatre fichiers. ldf se trouvent dans l’annuaire \Support\Schema de votre support d’installation ou de votre téléchargement.</span><span class="sxs-lookup"><span data-stu-id="def27-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="def27-185">Pour utiliser Ldifde. exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui est le maître de schéma, utilisez le format suivant:</span><span class="sxs-lookup"><span data-stu-id="def27-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="def27-186">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="def27-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="def27-187">Utilisez le paramètre b uniquement si vous êtes connecté en tant qu’un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="def27-187">Use the b parameter only if you are logged in as a different user.</span></span> <span data-ttu-id="def27-188">Pour plus d’informations sur les droits d’utilisateur requis, voir la section «privilèges d’administrateur et rôles» plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="def27-188">For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="def27-189">Pour utiliser Ldifde. exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui n’est pas le maître de schéma, utilisez le format suivant:</span><span class="sxs-lookup"><span data-stu-id="def27-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="def27-190">Pour plus d’informations sur l’utilisation de LDIFDE, voir l’article de la base de connaissances Microsoft 237677 «utilisation de LDIFDE pour importer et exporter [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)des objets d’annuaire dans Active Directory».</span><span class="sxs-lookup"><span data-stu-id="def27-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="def27-191">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="def27-191">In This Section</span></span>

  - [<span data-ttu-id="def27-192">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="def27-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="def27-193">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="def27-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="def27-194">Préparation des domaines pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="def27-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

