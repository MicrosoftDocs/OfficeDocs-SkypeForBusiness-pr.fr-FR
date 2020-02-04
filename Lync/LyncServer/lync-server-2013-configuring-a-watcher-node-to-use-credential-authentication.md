---
title: 'Lync Server 2013 : configuration d’un nœud FileSystemWatcher pour utiliser l’authentification des informations d’identification'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d0fa67c4ef2688035471d2290ead78123f73239
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="6a88a-102">Configuration d’un nœud FileSystemWatcher pour utiliser l’authentification des informations d’identification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a88a-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a88a-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6a88a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6a88a-104">Si votre ordinateur de nœud de l’observateur se trouve en dehors du réseau de périmètre, vous devez suivre une procédure légèrement différente pour configurer le nœud de l’observateur pour qu’il exécute des transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="6a88a-104">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions.</span></span> <span data-ttu-id="6a88a-105">Plus précisément, il est préférable de ne pas créer de pool d’applications fiable et d’application fiable, et vous devez installer un certificat qui permet au nœud d’observation d’envoyer des alertes à un ordinateur à l’intérieur du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="6a88a-105">Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network.</span></span> <span data-ttu-id="6a88a-106">Cela signifie que vous devez effectuer deux tâches distinctes :</span><span class="sxs-lookup"><span data-stu-id="6a88a-106">This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="6a88a-107">Mettre à jour l’appartenance au groupe d’administrateurs en lecture seule local de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="6a88a-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="6a88a-108">Installer les fichiers de configuration de nœud d’observation</span><span class="sxs-lookup"><span data-stu-id="6a88a-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="6a88a-109">Mise à jour de l’appartenance au groupe d’administrateurs en lecture seule locale RTC</span><span class="sxs-lookup"><span data-stu-id="6a88a-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="6a88a-110">Si votre nœud FileSystemWatcher se trouve en dehors du réseau de périmètre, vous devez ajouter le compte de service réseau au groupe d’administrateurs en lecture seule locale RTC sur l’ordinateur de nœud d’observation.</span><span class="sxs-lookup"><span data-stu-id="6a88a-110">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer.</span></span> <span data-ttu-id="6a88a-111">Pour cela, suivez la procédure ci-dessous sur le nœud d’observation :</span><span class="sxs-lookup"><span data-stu-id="6a88a-111">To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="6a88a-112">Cliquez sur **Démarrer**, cliquez avec le bouton droit sur **ordinateur**, puis cliquez sur **gérer**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="6a88a-113">Dans le gestionnaire de serveur, développez **configuration**, **utilisateurs et groupes locaux**, puis cliquez sur **groupes**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="6a88a-114">Dans le volet groupes, cliquez deux fois sur **RTC local en lecture seule**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="6a88a-115">Dans la boîte de dialogue Propriétés de l' **administrateur en lecture seule** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="6a88a-116">Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des comptes de service ou des groupes** , cliquez sur **emplacements**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="6a88a-117">Dans la boîte de dialogue **emplacements** , sélectionnez le nom de l’ordinateur du nœud d’observation, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="6a88a-118">Dans la zone **Entrez les noms des objets à sélectionner** , tapez **service réseau**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="6a88a-119">Dans la boîte de dialogue Propriétés de l' **administrateur en lecture seule locale RTC** , cliquez sur **OK**, puis fermez le **Gestionnaire de serveur**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="6a88a-120">Redémarrez l’ordinateur de nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="6a88a-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="6a88a-121">Installation des fichiers de configuration de nœud d’observation</span><span class="sxs-lookup"><span data-stu-id="6a88a-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="6a88a-122">Après le redémarrage de l’ordinateur de nœud d’observateur, l’étape suivante consiste à exécuter le fichier Watchernode. msi.</span><span class="sxs-lookup"><span data-stu-id="6a88a-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="6a88a-123">Pour exécuter ce fichier, ouvrez Lync Server 2013 Management Shell en cliquant sur **Démarrer**, puis sur **tous les programmes**, sur **Lync Server 2013**et sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6a88a-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="6a88a-124">Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (Vérifiez et spécifiez le chemin d’accès réel à votre copie de Watchernode. msi) :</span><span class="sxs-lookup"><span data-stu-id="6a88a-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="6a88a-125">Comme indiqué précédemment, Watchernode. msi peut également être exécuté à partir d’une fenêtre de commande.</span><span class="sxs-lookup"><span data-stu-id="6a88a-125">As noted previously, Watchernode.msi can also be run from a command window.</span></span> <span data-ttu-id="6a88a-126">Pour ouvrir une fenêtre de commande, cliquez sur <STRONG>Démarrer</STRONG>, cliquez avec le bouton droit sur <STRONG>Invite de commandes</STRONG>, puis cliquez sur <STRONG>Exécuter en tant qu’administrateur</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6a88a-126">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="6a88a-127">Lorsque la fenêtre de commande s’ouvre, tapez la même commande que celle présentée précédemment.</span><span class="sxs-lookup"><span data-stu-id="6a88a-127">When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="6a88a-p105">Le mode Négocier est utilisé chaque fois que le nœud observateur ne peut pas être configuré comme pool d’application approuvées. Dans ce mode, les administrateurs devront gérer les mots de passe des utilisateurs de test sur le nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="6a88a-p105">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool. In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

