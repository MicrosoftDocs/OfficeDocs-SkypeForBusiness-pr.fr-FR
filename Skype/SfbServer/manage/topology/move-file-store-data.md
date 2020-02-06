---
title: Déplacer les données du magasin de fichiers vers un nouveau magasin de fichiers dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si vous avez besoin de supprimer le serveur de fichiers agissant actuellement en tant que magasin de fichiers pour votre déploiement de Skype entreprise Server ou si vous devez apporter d’autres modifications pour rendre le stockage de fichiers actuel indisponible, vous devez tout d’abord créer un nouveau partage. Ensuite, procédez comme suit :'
ms.openlocfilehash: e1c4338e33e736c04dbb1a2a2e81a7233df65763
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817105"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="41c23-104">Déplacer les données du magasin de fichiers vers un nouveau magasin de fichiers dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="41c23-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="41c23-105">Si vous avez besoin de supprimer le serveur de fichiers agissant actuellement en tant que magasin de fichiers pour votre déploiement de Skype entreprise Server ou si vous devez apporter d’autres modifications pour rendre le stockage de fichiers actuel indisponible, vous devez tout d’abord créer un nouveau partage.</span><span class="sxs-lookup"><span data-stu-id="41c23-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="41c23-106">Ensuite, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="41c23-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="41c23-107">Fermez les services Skype entreprise Server qui utilisent le magasin de fichiers que vous envisagez de supprimer.</span><span class="sxs-lookup"><span data-stu-id="41c23-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="41c23-108">Définissez le magasin de fichiers dans le générateur de topologie et publiez les modifications pour rendre le nouveau magasin de fichiers disponible pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="41c23-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="41c23-109">Déplacez les données vers le nouveau magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="41c23-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="41c23-110">Redémarrez les serveurs ou services.</span><span class="sxs-lookup"><span data-stu-id="41c23-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="41c23-111">Vous pouvez également supprimer les partages de fichiers et dossier de fichiers anciens.</span><span class="sxs-lookup"><span data-stu-id="41c23-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="41c23-112">Pour déplacer les données du magasin de fichiers d’un magasin de fichiers vers un autre</span><span class="sxs-lookup"><span data-stu-id="41c23-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="41c23-113">Connectez-vous à un ordinateur en tant que membre du groupe RTCUniversersalServerAdmins ou CsServerAdministrator dans lequel Skype entreprise Server, outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="41c23-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2.  <span data-ttu-id="41c23-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="41c23-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="41c23-115">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. </span><span class="sxs-lookup"><span data-stu-id="41c23-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="41c23-116">Pour chaque pool de réalisateurs, directeur, serveur Standard Edition et pool frontal qui utilise le magasin de fichiers que vous envisagez de supprimer, sélectionnez le serveur ou le pool, cliquez sur **action**, puis cliquez sur **arrêter tous les services**.</span><span class="sxs-lookup"><span data-stu-id="41c23-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="41c23-117">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="41c23-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="41c23-118">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Générateur de topologie Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="41c23-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="41c23-119">Sélectionnez un serveur ou un pool qui utilise le magasin de fichiers et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="41c23-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="41c23-120">a.</span><span class="sxs-lookup"><span data-stu-id="41c23-120">a.</span></span> <span data-ttu-id="41c23-121">Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés**. </span><span class="sxs-lookup"><span data-stu-id="41c23-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="41c23-122">b.</span><span class="sxs-lookup"><span data-stu-id="41c23-122">b.</span></span> <span data-ttu-id="41c23-123">Dans **Modifier les propriétés**, sous **Associations**, puis sous **Magasin de fichiers**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="41c23-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="41c23-124">c.</span><span class="sxs-lookup"><span data-stu-id="41c23-124">c.</span></span> <span data-ttu-id="41c23-125">Dans **Définir un nouveau magasin de fichiers**, sous **Nom de domaine complet du serveur de fichiers**, saisissez le nom de domaine complet du serveur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="41c23-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="41c23-126">Sous **Partage de fichiers**, saisissez le nom de dossier pour le nouveau partage de fichiers et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="41c23-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="41c23-127">Cette étape définit un nouveau magasin de fichiers à utiliser dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="41c23-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="41c23-128">Définissez-le une seule fois, non pour chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="41c23-128">You define it only once, not for each server.</span></span> <span data-ttu-id="41c23-129">Avant de publier la topologie, vous devez créer le partage de fichiers sur le serveur de fichiers défini.</span><span class="sxs-lookup"><span data-stu-id="41c23-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="41c23-130">Pour plus d’informations, reportez-vous à la section [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="41c23-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="41c23-131">Pour chaque serveur ou pool qui utilise le magasin de fichiers, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="41c23-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="41c23-132">a.</span><span class="sxs-lookup"><span data-stu-id="41c23-132">a.</span></span> <span data-ttu-id="41c23-133">Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="41c23-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="41c23-134">b.</span><span class="sxs-lookup"><span data-stu-id="41c23-134">b.</span></span> <span data-ttu-id="41c23-135">Dans **Modifier les propriétés**, sous **Associations**, dans **Magasin de fichiers**, sélectionnez le nouveau partage de fichiers, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="41c23-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="41c23-136">Publiez la topologie, vérifiez l’état de la connexion, puis exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="41c23-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="41c23-137">Pour plus d’informations, reportez-vous à la section [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="41c23-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="41c23-138">Démarrez une invite de commandes : cliquez sur **Démarrer**, sur **exécuter**, puis tapez cmd. exe.</span><span class="sxs-lookup"><span data-stu-id="41c23-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="41c23-139">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="41c23-139">At the command line, type the following:</span></span>

     ```console
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > <span data-ttu-id="41c23-140">Le commutateur /S permet de copier sur des fichiers, des répertoires et des sous-répertoires.</span><span class="sxs-lookup"><span data-stu-id="41c23-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="41c23-141">Le commutateur /XF permet d’ignorer des fichiers nommés Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="41c23-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="41c23-142">Les versions actuelles du fichier robocopy.exe avec le commutateur /MT augmentent considérablement la vitesse de copie à l’aide de plusieurs threads.</span><span class="sxs-lookup"><span data-stu-id="41c23-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="41c23-143">Pour le commutateur/LOG, utilisez un chemin d’accès au répertoire et un nom de fichier journal sous la forme de C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="41c23-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="41c23-144">Ce commutateur crée un fichier journal d’opérations à l’emplacement nommé.</span><span class="sxs-lookup"><span data-stu-id="41c23-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="41c23-145">Lorsque la copie des données est terminée, dans le panneau de configuration de Lync Server, cliquez sur **Topology**, puis sur **Status**.</span><span class="sxs-lookup"><span data-stu-id="41c23-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="41c23-146">Pour chaque serveur et pool sur lesquels vous avez arrêté les services, sélectionnez le serveur ou pool, cliquez sur **Action**, puis sur **Démarrer tous les services**.         </span><span class="sxs-lookup"><span data-stu-id="41c23-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="41c23-p111">Supprimez l’ancien magasin de fichiers de la topologie et publiez la topologie. Pour plus d’informations, reportez-vous à la section [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="41c23-p111">Remove the old file store from the topology and then publish the topology. For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="41c23-149">(Facultatif) Connectez-vous à l’ordinateur qui contient le magasin de fichiers que vous venez de supprimer en tant que membre du groupe Administrateurs local ou du groupe Administrateurs de domaines et supprimez le partage de fichiers et le répertoire anciens.</span><span class="sxs-lookup"><span data-stu-id="41c23-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="41c23-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41c23-150">See also</span></span>


[<span data-ttu-id="41c23-151">Réattribuer un serveur à un autre magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="41c23-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="41c23-152">Supprimer un magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="41c23-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

