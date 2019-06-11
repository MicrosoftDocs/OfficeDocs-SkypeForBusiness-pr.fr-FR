---
title: 'Lync Server 2013: restauration des données d’analyse ou d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 803cb6050d4230653a13f1e3e66c2a092911c509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="295bf-102">Restauration de données d’analyse ou d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="295bf-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="295bf-103">_**Dernière modification de la rubrique:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="295bf-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="295bf-104">Il n’est pas nécessaire de restaurer les données de surveillance et d’archivage après un échec.</span><span class="sxs-lookup"><span data-stu-id="295bf-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="295bf-105">Toutefois, si la surveillance et l’archivage de données sont essentielles pour votre organisation, vous pouvez restaurer les données une fois la nouvelle création de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="295bf-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="295bf-106">La procédure suivante vous explique comment utiliser SQL Server Management Studio pour restaurer les données d’archivage et d’analyse des données.</span><span class="sxs-lookup"><span data-stu-id="295bf-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="295bf-107">Pour restaurer les données d’analyse ou d’archivage à partir d’un fichier de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="295bf-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="295bf-108">Ouvrez une session sur le serveur que vous restaurez en tant que membre du groupe Administrateurs sur l’ordinateur local ou un groupe disposant de droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="295bf-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="295bf-109">Ouvrez SQL Server Management Studio: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft SQL Server 2012** ou **Microsoft SQL Server 2008 R2**, puis cliquez sur **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="295bf-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="295bf-110">Dans **connexion au serveur**, connectez-vous à l’instance SQL Server en fournissant au moins le nom du serveur et les informations d’authentification.</span><span class="sxs-lookup"><span data-stu-id="295bf-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="295bf-111">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur **bases de données**, puis cliquez sur **restaurer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="295bf-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="295bf-112">Sous **Sélectionner une page**, cliquez sur **général**, puis dans la **base de données** , sélectionnez le nom de la base de données comme suit:</span><span class="sxs-lookup"><span data-stu-id="295bf-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="295bf-113">Pour une base de données d’archivage, sélectionnez **LcsLog**.</span><span class="sxs-lookup"><span data-stu-id="295bf-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="295bf-114">Pour une base de données d’enregistrement des détails des appels, sélectionnez **LcsCDR**.</span><span class="sxs-lookup"><span data-stu-id="295bf-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="295bf-115">Pour une base de données de qualité de l’apprentissage (QoE), sélectionnez **QoEMetrics**.</span><span class="sxs-lookup"><span data-stu-id="295bf-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="295bf-116">Cliquez sur **à partir de l’appareil**.</span><span class="sxs-lookup"><span data-stu-id="295bf-116">Click **From device**.</span></span>

7.  <span data-ttu-id="295bf-117">Sous **sélectionnez les jeux de sauvegarde à restaurer**, cliquez sur le fichier de sauvegarde, puis cliquez sur **restaurer**.</span><span class="sxs-lookup"><span data-stu-id="295bf-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="295bf-118">Sous **Sélectionner une page**, cliquez sur **options**, assurez-vous que le chemin d’accès et le chemin d’accès du fichier de données se trouvent dans le dossier approprié, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="295bf-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="295bf-119">Pour vous assurer que les listes de contrôle d’accès (ACL) sont correctes</span><span class="sxs-lookup"><span data-stu-id="295bf-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="295bf-120">Développez **bases de données**, développez la base de données d’archivage ou de surveillance, développez **sécurité**, puis **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="295bf-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="295bf-121">Vérifiez que le groupe de domaine RTCComponentUniversalServices existe en tant qu’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="295bf-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="295bf-122">Si RTCComponentUniversalServices n’existe pas sous **utilisateurs**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="295bf-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="295bf-123">Cliquez avec le bouton droit sur **utilisateurs**, puis cliquez sur **nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="295bf-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="295bf-124">Dans **nom de connexion**, tapez le nom de groupe manquant, RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="295bf-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="295bf-125">Sous **appartenance aux rôles de base de données**, sélectionnez l’autorisation **ServerRole** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="295bf-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="295bf-126">Vous n’avez pas besoin de redémarrer le service d’archivage ou de surveillance.</span><span class="sxs-lookup"><span data-stu-id="295bf-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

