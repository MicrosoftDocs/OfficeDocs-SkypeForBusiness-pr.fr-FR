---
title: Move File Store Data to a New File Store in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si vous devez supprimer le serveur de fichiers qui joue actuellement le rôle de magasin de fichiers pour votre déploiement Skype Entreprise Server 2015, ou si vous devez apporter d’autres modifications qui rendraient le magasin de fichiers actuel indisponible, vous devez d’abord créer un nouveau partage. Ensuite, vous devez effectuer les étapes suivantes :'
ms.openlocfilehash: 2d65e517b10a76013fbeb332b183b5b816e99083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119643"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="bc68e-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bc68e-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="bc68e-105">Si vous devez supprimer le serveur de fichiers qui joue actuellement le rôle de magasin de fichiers pour votre déploiement Skype Entreprise Server 2015, ou si vous devez apporter d’autres modifications qui rendraient le magasin de fichiers actuel indisponible, vous devez d’abord créer un nouveau partage.</span><span class="sxs-lookup"><span data-stu-id="bc68e-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="bc68e-106">Ensuite, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc68e-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="bc68e-107">Fermez les services Skype Entreprise Server 2015 qui utilisent le magasin de fichiers que vous prévoyez de supprimer.</span><span class="sxs-lookup"><span data-stu-id="bc68e-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="bc68e-108">Définissez le magasin de fichiers dans le Générateur de topologie et publiez les modifications pour rendre le nouveau magasin de fichiers disponible pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="bc68e-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="bc68e-109">Déplacez les données vers le nouveau magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bc68e-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="bc68e-110">Redémarrez les serveurs ou les services.</span><span class="sxs-lookup"><span data-stu-id="bc68e-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="bc68e-111">Éventuellement, supprimez l’ancien partage de fichiers et le dossier de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bc68e-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="bc68e-112">Pour déplacer les données du magasin de fichiers vers le nouveau magasin</span><span class="sxs-lookup"><span data-stu-id="bc68e-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="bc68e-113">Connectez-vous à un ordinateur en tant que membre du groupe RTCUniversersalServerAdmins ou CsServerAdministrator sur lequel les outils d’administration de Skype Entreprise Server 2015 sont installés.</span><span class="sxs-lookup"><span data-stu-id="bc68e-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="bc68e-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bc68e-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="bc68e-115">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.</span><span class="sxs-lookup"><span data-stu-id="bc68e-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="bc68e-116">Pour chaque pool directeur, directeur, serveur Standard Edition et pool frontal qui utilise le magasin de fichiers que vous prévoyez de supprimer, sélectionnez le serveur ou le pool, cliquez sur **Action,** puis cliquez sur Arrêter tous les **services.**</span><span class="sxs-lookup"><span data-stu-id="bc68e-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="bc68e-117">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bc68e-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="bc68e-118">Démarrez le Générateur de topologie : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server 2015,** puis sur Générateur d’topology Skype Entreprise **Server 2015.**</span><span class="sxs-lookup"><span data-stu-id="bc68e-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="bc68e-119">Sélectionnez un serveur ou un pool qui utilise le magasin de fichiers et faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc68e-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="bc68e-120">Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez **sur Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="bc68e-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="bc68e-121">Dans **Modifier les propriétés,** sous **Associations,** sous **Magasin de fichiers,** cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bc68e-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="bc68e-122">Dans **Définir un nouveau magasin de** fichiers, sous **FQDN** du serveur de fichiers, tapez le nom de domaine complet (FQDN) du serveur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bc68e-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="bc68e-123">Sous **Partage de fichiers,** tapez le nom du dossier du nouveau partage de fichiers, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="bc68e-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="bc68e-124">Cette étape définit un nouveau magasin de fichiers à utiliser dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="bc68e-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="bc68e-125">Vous ne la définissez qu’une seule fois, et non pour chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="bc68e-125">You define it only once, not for each server.</span></span> <span data-ttu-id="bc68e-126">Avant de publier la topologie, vous devez créer le partage de fichiers défini sur le serveur de fichiers défini.</span><span class="sxs-lookup"><span data-stu-id="bc68e-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="bc68e-127">Pour plus d’informations, voir [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="bc68e-127">For details, see [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span></span>

11. <span data-ttu-id="bc68e-128">Pour chaque serveur ou pool qui utilise le magasin de fichiers, faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc68e-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="bc68e-129">Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="bc68e-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="bc68e-130">Dans **Modifier les propriétés,** sous **Associations,** **dans** le magasin de fichiers, sélectionnez le nouveau partage de fichiers, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc68e-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="bc68e-131">Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Skype Entreprise Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="bc68e-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="bc68e-132">Pour plus d’informations, voir [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="bc68e-132">For details, see [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span></span>

15. <span data-ttu-id="bc68e-133">Démarrez une invite de commandes : cliquez **sur Démarrer,** sur **Exécuter,** puis tapez cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="bc68e-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="bc68e-134">Dans la ligne de commande, tapez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="bc68e-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="bc68e-135">Le commutateur /S copie les fichiers, répertoires et sous-répertoires.</span><span class="sxs-lookup"><span data-stu-id="bc68e-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="bc68e-136">Le commutateur /XF ignore tous les fichiers nommés Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="bc68e-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="bc68e-137">Les versions actuelles de robocopy.exe avec le commutateur /MT offrent une vitesse de copie bien plus élevée en ayant recours à plusieurs threads.</span><span class="sxs-lookup"><span data-stu-id="bc68e-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="bc68e-138">Pour le commutateur /LOG, utilisez un chemin d’accès au répertoire et un nom de fichier journal sous la forme C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="bc68e-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="bc68e-139">Ce commutateur crée un fichier journal d’opérations à l’emplacement nommé.</span><span class="sxs-lookup"><span data-stu-id="bc68e-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="bc68e-140">Lorsque la copie des données est terminée, dans le Panneau de contrôle Lync Server, cliquez sur **Topologie,** puis sur **État**.</span><span class="sxs-lookup"><span data-stu-id="bc68e-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="bc68e-141">Pour chaque serveur ou pool sur lequel vous avez arrêté les services, sélectionnez le serveur ou le pool, cliquez sur **Action,** puis cliquez sur **Démarrer tous les services.**</span><span class="sxs-lookup"><span data-stu-id="bc68e-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="bc68e-142">Supprimez l’ancien magasin de fichiers de la topologie, puis publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="bc68e-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="bc68e-143">Pour plus d’informations, voir [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="bc68e-143">For details, see [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span></span>

20. <span data-ttu-id="bc68e-144">(Facultatif) Ouvrez une session sur l’ordinateur qui contient le magasin de fichiers que vous venez de supprimer en tant que membre du groupe Administrateurs local ou du groupe Administrateurs de domaine, puis supprimez l’ancien répertoire et l’ancien partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bc68e-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc68e-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc68e-145">See also</span></span>

<span data-ttu-id="bc68e-146">[Réattribuer un serveur à un magasin de fichiers différent](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="bc68e-146">[Reassign a Server to a Different File Store](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span></span>

<span data-ttu-id="bc68e-147">[Supprimer un magasin de fichiers](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="bc68e-147">[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span></span>