---
title: 'Lync Server 2013: sauvegarde de données principales et de paramètres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1737dac3369361b0937e6b870839e11e5706e41a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="87482-102">Sauvegarder les données principales et les paramètres dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87482-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87482-103">_**Dernière modification de la rubrique:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="87482-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="87482-104">Les procédures suivantes permettent d’utiliser les applets de commande Lync Server Management Shell pour créer des fichiers de sauvegarde des paramètres et des données pour les services principaux.</span><span class="sxs-lookup"><span data-stu-id="87482-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="87482-105">Pour plus d’informations sur les outils utilisés dans cette section, y compris l’endroit où ils se trouvent, voir [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013: outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="87482-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="87482-106">Pour plus d’informations sur l’archivage et l’analyse des données, voir [sauvegarder des bases de données d’archivage et de surveillance dans Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="87482-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87482-107">Dans cette section, vous pouvez sauvegarder le magasin central de gestion en incluant les paramètres et la configuration de l’archivage et de la surveillance.</span><span class="sxs-lookup"><span data-stu-id="87482-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="87482-108">Vous pouvez exécuter les applets de commande décrites dans cette section localement ou à distance.</span><span class="sxs-lookup"><span data-stu-id="87482-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="87482-109">Pour sauvegarder les données et paramètres de base</span><span class="sxs-lookup"><span data-stu-id="87482-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="87482-110">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="87482-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="87482-111">Pour stocker les sauvegardes que vous créez dans les étapes suivantes, créez un dossier partagé et mettez à jour le chemin d’accès référencé par **$Backup** vers le nouveau dossier partagé.</span><span class="sxs-lookup"><span data-stu-id="87482-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="87482-112">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="87482-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="87482-113">Sauvegardez le fichier de configuration du magasin de gestion central.</span><span class="sxs-lookup"><span data-stu-id="87482-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="87482-114">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="87482-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="87482-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="87482-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="87482-116">Cette étape exporte la topologie de votre serveur Lync, les stratégies et les paramètres de configuration vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="87482-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="87482-117">Aucune autre étape n’est nécessaire pour sauvegarder les données de topologie.</span><span class="sxs-lookup"><span data-stu-id="87482-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="87482-118">Copiez le fichier de configuration de la boutique de gestion centralisée\\sauvegardé dans $Backup.</span><span class="sxs-lookup"><span data-stu-id="87482-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="87482-119">Sauvegarder les données de service des informations de géolocalisation.</span><span class="sxs-lookup"><span data-stu-id="87482-119">Back up Location Information service data.</span></span> <span data-ttu-id="87482-120">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="87482-120">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="87482-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="87482-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="87482-122">Copiez le fichier de configuration de service des informations de géolocalisation sur $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="87482-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="87482-123">Sauvegardez des données utilisateur sur chaque base de données principale d’un pool frontal et sur tous les serveurs Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="87482-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="87482-124">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="87482-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="87482-125">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="87482-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="87482-126">Copiez le fichier utilisateur sauvegardé dans $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="87482-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="87482-127">Dans chaque liste qui exécute l’application Response Group, sauvegardez la configuration de Response Group.</span><span class="sxs-lookup"><span data-stu-id="87482-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="87482-128">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="87482-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="87482-129">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="87482-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="87482-130">Exemple :</span><span class="sxs-lookup"><span data-stu-id="87482-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="87482-131">Copiez le fichier de configuration de groupe de réponse sauvegardé\\dans $Backup.</span><span class="sxs-lookup"><span data-stu-id="87482-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

