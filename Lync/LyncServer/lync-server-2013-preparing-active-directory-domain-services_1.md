---
title: 'Lync Server 2013 : préparation des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b6e0e44367af86ea42099241ef3d9bbfa750133
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="cc411-102">Préparation des services de domaine Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc411-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc411-103">_**Dernière modification de la rubrique :** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="cc411-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="cc411-104">Dans Lync Server 2013, vous pouvez utiliser l’Assistant Déploiement Lync Server pour préparer les services de domaine Active Directory ou vous pouvez utiliser les applets de commande Lync Server Management Shell directement.</span><span class="sxs-lookup"><span data-stu-id="cc411-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="cc411-105">Vous pouvez également utiliser la ligne de commande directement sur vos contrôleurs de domaine, comme expliqué plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="cc411-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="cc411-106">L’Assistant Déploiement de Lync Server vous guide à travers chaque tâche de préparation d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cc411-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="cc411-107">L’Assistant Déploiement exécute des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cc411-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="cc411-108">Cet outil est utile pour les environnements avec une topologie à un seul domaine et à une seule forêt ou avec une autre topologie semblable.</span><span class="sxs-lookup"><span data-stu-id="cc411-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc411-109">Vous pouvez déployer Lync Server dans une forêt ou un domaine où des contrôleurs de domaine exécutent des versions 32 bits de certains systèmes d’exploitation (pour plus d’informations, consultez la rubrique <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure Requirements for Lync Server 2013</A>).</span><span class="sxs-lookup"><span data-stu-id="cc411-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="cc411-110">Toutefois, vous ne pouvez pas utiliser l’Assistant Déploiement Lync Server pour exécuter la préparation des schémas, des forêts et des domaines dans ces environnements, car l’Assistant Déploiement et les fichiers de prise en charge sont 64 bits uniquement.</span><span class="sxs-lookup"><span data-stu-id="cc411-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="cc411-111">À la place, vous pouvez utiliser ldifde.exe et les fichiers .ldf associés sur un contrôleur de domaine 32 bits pour préparer le schéma, la forêt et le domaine.</span><span class="sxs-lookup"><span data-stu-id="cc411-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="cc411-112">Voir la section « Utilisation des applets de commande et de Ldifde.exe » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="cc411-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="cc411-113">Vous pouvez utiliser des applets de commande Lync Server Management Shell pour exécuter des tâches à distance ou pour des environnements plus complexes.</span><span class="sxs-lookup"><span data-stu-id="cc411-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="cc411-114">Conditions préalables à la préparation d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc411-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="cc411-115">Vous devez exécuter les étapes de préparation d’Active Directory sur un ordinateur exécutant Windows Server 2012, Windows Server 2012 R2 ou Windows Server 2008 R2 avec SP1 (64 bits).</span><span class="sxs-lookup"><span data-stu-id="cc411-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="cc411-116">La préparation d’Active Directory requiert Lync Server Management Shell et OCSCore.</span><span class="sxs-lookup"><span data-stu-id="cc411-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="cc411-117">Les composants suivants sont requis pour exécuter les tâches de préparation d’Active Directory :</span><span class="sxs-lookup"><span data-stu-id="cc411-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="cc411-118">Composants principaux de Lync Server (OCScore. msi)</span><span class="sxs-lookup"><span data-stu-id="cc411-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc411-119">Si vous envisagez d’utiliser Lync Server Management Shell pour la préparation d’Active Directory, vous devez d’abord exécuter l’Assistant Déploiement de Lync Server pour installer les composants principaux.</span><span class="sxs-lookup"><span data-stu-id="cc411-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="cc411-120">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="cc411-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc411-121">Pour Windows Server 2012 et Windows Server 2012 R2, vous devez installer et activer .NET Framework 4,5 à l’aide du gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="cc411-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="cc411-122">Pour plus d’informations, voir « Microsoft .NET Framework 4,5 » dans la rubrique relative <A href="lync-server-2013-additional-software-requirements.md">à la configuration logicielle requise pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cc411-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="cc411-123">Pour Windows Server&nbsp;2008&nbsp;R2, téléchargez et installez <A href="https://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> à partir du site Web de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc411-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="https://www.microsoft.com/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="cc411-124">Outils d’administration de serveur distant (RSAT)</span><span class="sxs-lookup"><span data-stu-id="cc411-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc411-125">Certains outils RSAT sont nécessaires si vous exécutez les étapes de préparation d’Active Directory sur un serveur membre plutôt que sur un contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="cc411-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="cc411-126">Installez les composants logiciels enfichables AD DS et les outils en ligne de commande et le module Active Directory pour Windows PowerShell à partir du nœud AD DS et AD LDS Tools dans le gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="cc411-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="cc411-127">Microsoft Visual C++ 11 Redistributable</span><span class="sxs-lookup"><span data-stu-id="cc411-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc411-p107">Le programme d’installation vous invite à l’installer s’il n’est pas déjà sur l’ordinateur. Le package vous est fourni, il est inutile de l’acquérir séparément.</span><span class="sxs-lookup"><span data-stu-id="cc411-p107">Setup prompts you to install this prerequisite if it is not already installed on the computer. The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="cc411-130">Windows PowerShell 3,0 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="cc411-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="cc411-131">Pour Windows Server 2012 et Windows Server 2012 R2, Windows PowerShell 3,0 doit être inclus dans votre installation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc411-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="cc411-132">Pour Windows Server 2008 R2, vous devez installer ou effectuer une mise à niveau vers Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="cc411-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="cc411-133">Pour plus d’informations, consultez la rubrique [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="cc411-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="cc411-134">Droits et rôles d’administrateur</span><span class="sxs-lookup"><span data-stu-id="cc411-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="cc411-135">Le tableau ci-après répertorie les droits et rôles d’administration requis pour chaque tâche de préparation d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cc411-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="cc411-136">Droits de l’utilisateur requis pour la préparation d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc411-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc411-137">Procedure</span><span class="sxs-lookup"><span data-stu-id="cc411-137">Procedure</span></span></th>
<th><span data-ttu-id="cc411-138">Droits ou rôles</span><span class="sxs-lookup"><span data-stu-id="cc411-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc411-139">Préparation d’un schéma</span><span class="sxs-lookup"><span data-stu-id="cc411-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="cc411-140">Membre du groupe Administrateurs du schéma pour le domaine racine de la forêt et droits d’administrateur sur le contrôleur de schéma</span><span class="sxs-lookup"><span data-stu-id="cc411-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc411-141">Préparation d’une forêt</span><span class="sxs-lookup"><span data-stu-id="cc411-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="cc411-142">Membre du groupe Administrateurs de l’entreprise pour la forêt</span><span class="sxs-lookup"><span data-stu-id="cc411-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc411-143">Préparation d’un domaine</span><span class="sxs-lookup"><span data-stu-id="cc411-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="cc411-144">Membre du groupe Administrateurs de l’entreprise ou Administrateurs du domaine pour le domaine spécifié</span><span class="sxs-lookup"><span data-stu-id="cc411-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="cc411-145">Applets de commande de préparation d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc411-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="cc411-146">Le tableau suivant compare les applets de commande Lync Server Management Shell utilisées pour préparer AD DS aux commandes LcsCmd utilisées pour préparer AD DS dans Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="cc411-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="cc411-147">Applets de commande par rapport à LcsCmd</span><span class="sxs-lookup"><span data-stu-id="cc411-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc411-148">Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cc411-148">Cmdlets</span></span></th>
<th><span data-ttu-id="cc411-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="cc411-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc411-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="cc411-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="cc411-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span><span class="sxs-lookup"><span data-stu-id="cc411-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc411-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="cc411-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="cc411-153">Lcscmd /forest /action:CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="cc411-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc411-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="cc411-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="cc411-155">Lcscmd /forest /action:ForestPrep</span><span class="sxs-lookup"><span data-stu-id="cc411-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc411-156">Disable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="cc411-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="cc411-157">Lcscmd /forest /action:ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="cc411-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc411-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="cc411-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="cc411-159">Lcscmd /forest /action:CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="cc411-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc411-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="cc411-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="cc411-161">Lcscmd /domain /action:DomainPrep</span><span class="sxs-lookup"><span data-stu-id="cc411-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc411-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="cc411-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="cc411-163">Lcscmd /domain /action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="cc411-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc411-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="cc411-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="cc411-165">Lcscmd /domain /action:CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="cc411-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="cc411-166">Configuration requise pour des services de domaine Active Directory verrouillés</span><span class="sxs-lookup"><span data-stu-id="cc411-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="cc411-167">Si l’héritage des autorisations est désactivé ou que les autorisations des utilisateurs authentifiés doivent être désactivées dans votre organisation, vous devez exécuter des étapes supplémentaires dans le cadre de la procédure de préparation d’un domaine.</span><span class="sxs-lookup"><span data-stu-id="cc411-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="cc411-168">Pour plus d’informations, reportez-vous à la rubrique [préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="cc411-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="cc411-169">Autorisations de conteneur personnalisé</span><span class="sxs-lookup"><span data-stu-id="cc411-169">Custom Container Permissions</span></span>

<span data-ttu-id="cc411-170">Si votre organisation utilise des conteneurs personnalisés à la place des trois conteneurs intégrés (Utilisateurs, Ordinateurs et Contrôleurs de domaine), vous devez octroyer au groupe Utilisateurs authentifiés un accès en lecture aux conteneurs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="cc411-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="cc411-171">L’accès en lecture aux conteneurs est obligatoire pour la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="cc411-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="cc411-172">Pour plus d’informations, consultez la rubrique [Preparing Domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span><span class="sxs-lookup"><span data-stu-id="cc411-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="cc411-173">Utilisation des applets de commande et de Ldifde.exe</span><span class="sxs-lookup"><span data-stu-id="cc411-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="cc411-174">L’étape **préparer le schéma** de l’Assistant Déploiement de Lync Server et de l’applet de commande **install-CsAdServerSchema** étend le schéma Active Directory sur les contrôleurs de domaine exécutant un système d’exploitation 64 bits.</span><span class="sxs-lookup"><span data-stu-id="cc411-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="cc411-175">Si vous devez étendre le schéma Active Directory sur un contrôleur de domaine qui exécute un système d’exploitation 32 bits, vous pouvez exécuter l’applet de commande **Install-CsAdServerSchema** à distance depuis un serveur membre (approche recommandée).</span><span class="sxs-lookup"><span data-stu-id="cc411-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="cc411-176">Si toutefois vous devez exécuter la préparation du schéma directement sur le contrôleur de domaine, vous pouvez utiliser l’outil Ldifde.exe pour importer les fichiers de schéma.</span><span class="sxs-lookup"><span data-stu-id="cc411-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="cc411-177">L’outil Ldifde.exe est livré avec la plupart des versions du système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="cc411-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="cc411-p112">Si vous utilisez Ldife.exe pour importer les fichiers de schéma, vous devez importer les quatre fichiers, même si vous procédez à une migration depuis une version précédente ou à une nouvelle installation. Vous devez les importer dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="cc411-p112">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation. You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="cc411-180">ExternalSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="cc411-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="cc411-181">ServerSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="cc411-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="cc411-182">BackCompatSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="cc411-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="cc411-183">VersionSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="cc411-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc411-184">Les quatre fichiers .ldf se trouvent dans le répertoire \Support\Schema de votre support d’installation ou de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="cc411-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="cc411-185">Pour utiliser Ldifde.exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui est également le contrôleur de schéma, utilisez le format suivant :</span><span class="sxs-lookup"><span data-stu-id="cc411-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="cc411-186">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="cc411-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="cc411-p113">Utilisez le paramètre b seulement si vous êtes connecté en tant qu’un autre utilisateur. Pour plus d’informations sur les droits d’utilisateur requis, voir la section « Droits et rôles d’administrateur » abordée précédemment dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="cc411-p113">Use the b parameter only if you are logged in as a different user. For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="cc411-189">Pour utiliser Ldifde.exe pour importer les quatre fichiers de schéma sur un contrôleur de domaine qui n’est pas le contrôleur de schéma, utilisez le format suivant :</span><span class="sxs-lookup"><span data-stu-id="cc411-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="cc411-190">Pour plus d’informations sur l’utilisation de LDIFDE, consultez l’article 237677 de la base de connaissances Microsoft, « utilisation de LDIFDE pour importer et [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204)exporter des objets d’annuaire dans Active Directory », à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="cc411-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cc411-191">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cc411-191">In This Section</span></span>

  - [<span data-ttu-id="cc411-192">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc411-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="cc411-193">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc411-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="cc411-194">Préparation des domaines pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc411-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

