---
title: 'Lync Server 2013 : restauration des données de surveillance ou d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5be8d5409a5770ef2ee928075c147c126ce4219a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="6bcd4-102">Restauration des données de surveillance ou d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bcd4-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bcd4-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="6bcd4-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="6bcd4-104">La restauration des données de surveillance et d’archivage n’est pas nécessaire pour que Lync Server fonctionne après une défaillance.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="6bcd4-105">Toutefois, si les données de surveillance et d’archivage sont essentielles pour votre organisation, vous pouvez restaurer les données après avoir recréé les bases de données.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="6bcd4-106">La procédure suivante explique comment utiliser SQL Server Management Studio pour restaurer des données d’archivage ou de surveillance.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="6bcd4-107">Pour restaurer les données de surveillance ou d’archivage à partir d’un fichier de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="6bcd4-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="6bcd4-108">Ouvrez une session sur le serveur que vous restaurez en tant que membre du groupe Administrateurs sur l’ordinateur local ou un groupe avec des droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="6bcd4-109">Ouvrez SQL Server Management Studio : cliquez **sur Démarrer**, **sur tous les programmes**, sur **Microsoft SQL Server 2012** ou **Microsoft SQL Server 2008 R2**, puis sur **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="6bcd4-110">Dans **Se connecter au serveur**, connectez-vous à l’instance SQL Server en fournissant au moins le nom du serveur et les informations d’authentification.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="6bcd4-111">Dans **Explorateur d’objets**, cliquez avec le bouton droit sur **Bases de données**, puis cliquez sur **Restaurer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="6bcd4-112">Sous **Sélectionner une page**, cliquez sur **Général**, puis dans **Vers la base de données** sélectionnez le nom de la base de données comme suit :</span><span class="sxs-lookup"><span data-stu-id="6bcd4-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="6bcd4-113">Pour une base de données d’archivage, sélectionnez **LcsLog**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="6bcd4-114">Pour une base de données CDR (enregistrement des détails des appels), sélectionnez **LcsCDR**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="6bcd4-115">Pour une base de données QoE (qualité de l’expérience), sélectionnez **QoEMetrics**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="6bcd4-116">Cliquez sur **À partir de l’unité**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-116">Click **From device**.</span></span>

7.  <span data-ttu-id="6bcd4-117">Sous **Sélectionnez les jeux de sauvegarde à restaurer**, cliquez sur le fichier de sauvegarde, puis cliquez sur **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="6bcd4-118">Sous **Sélectionner une page**, cliquez sur **Options**, vérifiez que le chemin d’accès du fichier de données et que le chemin d’accès du journal sont dans le dossier voulu, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="6bcd4-119">Pour vous assurer que les listes de contrôle d’accès (ACL) sont correctes</span><span class="sxs-lookup"><span data-stu-id="6bcd4-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="6bcd4-120">Développez **Bases de données**, développez la base de données d’archivage ou de surveillance, développez **Sécurité**, puis développez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="6bcd4-121">Vérifiez que le groupe de domaines RTCComponentUniversalServices existe en tant qu’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="6bcd4-122">Si RTCComponentUniversalServices n’existe pas sous **utilisateurs**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6bcd4-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="6bcd4-123">Cliquez avec le bouton droit sur **Utilisateurs**, puis sur **Nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="6bcd4-124">Dans **nom de connexion**, tapez le nom de groupe manquant, RTCComponentUniversalServices.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="6bcd4-125">Sous **Appartenance au rôle de base de données**, sélectionnez l’autorisation **ServerRole**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6bcd4-126">Vous n’avez pas besoin de redémarrer le service d’archivage ou de surveillance.</span><span class="sxs-lookup"><span data-stu-id="6bcd4-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

