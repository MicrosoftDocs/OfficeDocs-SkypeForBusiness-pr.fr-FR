---
title: Déplacer des données de magasin de fichiers vers un nouveau magasin de fichiers dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/30/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si vous devez supprimer le serveur de fichiers qui est actuellement agissant en tant que le magasin de fichiers pour votre Skype pour le déploiement de Business Server 2015, ou si vous devez effectuer d’autres modifications que le fichier actuel stockent pas disponible, vous devez tout d’abord créer un nouveau partage. Ensuite, procédez comme suit :'
ms.openlocfilehash: cb79fe34afee093647b7d871bdd3096ce6040f7a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568949"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="66b77-104">Déplacer des données de magasin de fichiers vers un nouveau magasin de fichiers dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="66b77-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="66b77-105">Si vous devez supprimer le serveur de fichiers qui est actuellement agissant en tant que le magasin de fichiers pour votre Skype pour le déploiement de Business Server 2015, ou si vous devez effectuer d’autres modifications que le fichier actuel stockent pas disponible, vous devez tout d’abord créer un nouveau partage.</span><span class="sxs-lookup"><span data-stu-id="66b77-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="66b77-106">Ensuite, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="66b77-106">Then you need to perform the following steps:</span></span>
  
1. <span data-ttu-id="66b77-107">Arrêtez le Skype pour les services Business Server 2015 qui utilisent le magasin de fichiers que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="66b77-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>
    
2. <span data-ttu-id="66b77-108">Définir le magasin de fichiers dans le Générateur de topologie et de publier les modifications pour rendre le nouveau fichier stocker disponibles pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="66b77-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>
    
3. <span data-ttu-id="66b77-109">Déplacez les données vers le nouveau magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="66b77-109">Move the data to the new file store.</span></span>
    
4. <span data-ttu-id="66b77-110">Redémarrez les serveurs ou services.</span><span class="sxs-lookup"><span data-stu-id="66b77-110">Restart the servers or services.</span></span>
    
5. <span data-ttu-id="66b77-111">Vous pouvez également supprimer les partages de fichiers et dossier de fichiers anciens.</span><span class="sxs-lookup"><span data-stu-id="66b77-111">Optionally, remove the old file share and file folder.</span></span>
    
### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="66b77-112">Pour déplacer les données du magasin de fichiers d’un magasin de fichiers vers un autre</span><span class="sxs-lookup"><span data-stu-id="66b77-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="66b77-113">Ouvrez une session un ordinateur en tant que membre du groupe RTCUniversersalServerAdmins ou CsServerAdministrator où le Skype pour Business Server 2015, outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="66b77-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>
    
2.  <span data-ttu-id="66b77-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="66b77-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="66b77-115">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. </span><span class="sxs-lookup"><span data-stu-id="66b77-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span> 
    
4. <span data-ttu-id="66b77-116">Pour chaque pool directeur, directeur, serveur Standard Edition server et le pool frontal qui utilise le magasin de fichiers que vous souhaitez supprimer, sélectionnez le serveur ou pool, cliquez sur **Action**, puis cliquez sur **Arrêter tous les services**.</span><span class="sxs-lookup"><span data-stu-id="66b77-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span> 
    
5. <span data-ttu-id="66b77-117">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="66b77-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
6. <span data-ttu-id="66b77-118">Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="66b77-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
7. <span data-ttu-id="66b77-119">Sélectionnez un serveur ou un pool qui utilise le magasin de fichiers et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="66b77-119">Select a server or pool that uses the file store, and do the following:</span></span>
    
1. <span data-ttu-id="66b77-120">Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés**. </span><span class="sxs-lookup"><span data-stu-id="66b77-120">Right-click the server or pool, and then click **Edit Properties**.</span></span> 
    
2. <span data-ttu-id="66b77-121">Dans **Modifier les propriétés**, sous **Associations**, puis sous **Magasin de fichiers**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="66b77-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>
    
3. <span data-ttu-id="66b77-p103">Dans **Définir un nouveau magasin de fichiers**, sous **Nom de domaine complet du serveur de fichiers**, saisissez le nom de domaine complet du serveur de fichiers. Sous **Partage de fichiers**, saisissez le nom de dossier pour le nouveau partage de fichiers et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="66b77-p103">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server. Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66b77-124">Cette étape définit un nouveau magasin de fichiers à utiliser dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="66b77-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="66b77-125">Définissez-le une seule fois, non pour chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="66b77-125">You define it only once, not for each server.</span></span> <span data-ttu-id="66b77-126">Avant de publier la topologie, vous devez créer le partage de fichiers sur le serveur de fichiers défini.</span><span class="sxs-lookup"><span data-stu-id="66b77-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="66b77-127">Pour plus d’informations, voir [définir le magasin de fichiers pour le serveur frontal](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="66b77-127">For details, see [Define the File Store for the Front End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span> 
  
8. <span data-ttu-id="66b77-128">Pour chaque serveur ou pool qui utilise le magasin de fichiers, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="66b77-128">For each server or pool that uses the file store, do the following:</span></span>
    
1. <span data-ttu-id="66b77-129">Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="66b77-129">Right-click the server or pool, and then click **Edit properties**.</span></span>
    
2. <span data-ttu-id="66b77-130">Dans **Modifier les propriétés**, sous **Associations**, dans **Magasin de fichiers**, sélectionnez le nouveau partage de fichiers, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="66b77-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>
    
9. <span data-ttu-id="66b77-131">Publier la topologie, vérifiez le statut de réplication et exécutez le Skype pour l’Assistant de déploiement Business Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="66b77-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="66b77-132">Pour plus d’informations, voir [Procédures communes de suppression de Lync Servers and Components](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="66b77-132">For details, see [Common Procedures for Removing Lync Servers and Components](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>
    
10. <span data-ttu-id="66b77-133">Démarrez une invite de commandes : cliquez sur **Démarrer**, sur **exécuter**, puis tapez cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="66b77-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>
    
11. <span data-ttu-id="66b77-134">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="66b77-134">At the command line, type the following:</span></span>
    
  ```
  Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
  ```

    > [!TIP]
    > <span data-ttu-id="66b77-135">Le commutateur /S permet de copier sur des fichiers, des répertoires et des sous-répertoires.</span><span class="sxs-lookup"><span data-stu-id="66b77-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="66b77-136">Le commutateur /XF permet d’ignorer des fichiers nommés Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="66b77-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="66b77-137">Les versions actuelles du fichier robocopy.exe avec le commutateur /MT augmentent considérablement la vitesse de copie à l’aide de plusieurs threads.</span><span class="sxs-lookup"><span data-stu-id="66b77-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="66b77-138">Pour le commutateur /LOG, utilisez un chemin et nom du fichier répertoire sous la forme de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="66b77-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="66b77-139">Ce commutateur crée un fichier journal d’opérations à l’emplacement nommé.</span><span class="sxs-lookup"><span data-stu-id="66b77-139">This switch creates a log file of operations at the named location.</span></span> 
  
12. <span data-ttu-id="66b77-140">Lorsque la copie des données est terminée, dans le panneau de configuration de Lync Server, cliquez sur **la topologie**, puis cliquez sur **état**.</span><span class="sxs-lookup"><span data-stu-id="66b77-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>
    
13. <span data-ttu-id="66b77-141">Pour chaque serveur et pool sur lesquels vous avez arrêté les services, sélectionnez le serveur ou pool, cliquez sur **Action**, puis sur **Démarrer tous les services**.</span><span class="sxs-lookup"><span data-stu-id="66b77-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span> 
    
14. <span data-ttu-id="66b77-142">Supprimez l’ancien magasin de fichiers de la topologie et publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="66b77-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="66b77-143">Pour plus d’informations, voir [Supprimer un magasin de fichiers](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="66b77-143">For details, see [Remove a file store](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>
    
15. <span data-ttu-id="66b77-144">(Facultatif) Connectez-vous à l’ordinateur qui contient le magasin de fichiers que vous venez de supprimer en tant que membre du groupe Administrateurs local ou du groupe Administrateurs de domaines et supprimez le partage de fichiers et le répertoire anciens.</span><span class="sxs-lookup"><span data-stu-id="66b77-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="66b77-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66b77-145">See also</span></span>

[<span data-ttu-id="66b77-146">Réattribuer un serveur vers un autre magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="66b77-146">Reassign a Server to a Different File Store</span></span>](http://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)
  
[<span data-ttu-id="66b77-147">Supprimer un magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="66b77-147">Remove a file store</span></span>](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)