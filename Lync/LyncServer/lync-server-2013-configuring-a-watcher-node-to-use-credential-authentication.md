---
title: 'Lync Server 2013 : configuration d’un nœud observateur pour utiliser l’authentification des informations d’identification'
description: 'Lync Server 2013 : configuration d’un nœud observateur pour utiliser l’authentification des informations d’identification.'
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
ms.openlocfilehash: b65d4e3f90b27aac69b8569472ac9896766e093e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576320"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="d2bef-103">Configuration d’un nœud observateur pour utiliser l’authentification des informations d’identification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2bef-103">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2bef-104">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d2bef-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d2bef-p101">Si votre ordinateur de nœud observateur se trouve en dehors du réseau de périmètre, vous devez suivre une procédure légèrement différente afin de configurer ce nœud observateur pour qu’il exécute les transactions synthétiques. Surtout, évitez de créer un pool d’applications approuvées et une application approuvée. En revanche, vous devez installer un certificat permettant au nœud observateur d’envoyer des alertes à un ordinateur à l’intérieur du réseau de périmètre. En d’autres termes, vous devez effectuer deux tâches distinctes :</span><span class="sxs-lookup"><span data-stu-id="d2bef-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="d2bef-108">Mettre à jour l’appartenance au groupe « RTC Local Read-only Administrators » de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="d2bef-108">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="d2bef-109">Installer les fichiers de configuration du nœud observateur</span><span class="sxs-lookup"><span data-stu-id="d2bef-109">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="d2bef-110">Mise à jour de l’appartenance au groupe « RTC Local Read-Only Administrators »</span><span class="sxs-lookup"><span data-stu-id="d2bef-110">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="d2bef-p102">Si votre ordinateur de nœud observateur se trouve en dehors du réseau de périmètre, vous devez ajouter le compte Service réseau au groupe « RTC Local Read-only Administrators » sur l’ordinateur de nœud observateur. Pour cela, procédez comme suit sur le nœud observateur :</span><span class="sxs-lookup"><span data-stu-id="d2bef-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="d2bef-113">Cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Ordinateur** et cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-113">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="d2bef-114">Dans le Gestionnaire de serveur, développez **Configuration**, **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-114">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="d2bef-115">Dans le volet Groupes, double-cliquez sur **RTC Local Read-only Administrators**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-115">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="d2bef-116">Dans la boîte de dialogue **RTC Local Read-only Administrators - Propriétés**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-116">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="d2bef-117">Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des comptes de service ou des groupes**, cliquez sur **Emplacements**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-117">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="d2bef-118">Dans la boîte de dialogue **Emplacements**, sélectionnez le nom de l’ordinateur de nœud observateur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-118">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="d2bef-119">Dans la zone **Entrez les noms d’objets à sélectionner**, tapez **Service réseau**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-119">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="d2bef-120">Dans la boîte de dialogue **RTC Local Read-only Administrators - Propriétés**, cliquez sur **OK**, puis fermez le **Gestionnaire de serveur**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-120">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="d2bef-121">Redémarrez l’ordinateur de nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="d2bef-121">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="d2bef-122">Installation des fichiers de configuration du nœud observateur</span><span class="sxs-lookup"><span data-stu-id="d2bef-122">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="d2bef-123">Une fois que l’ordinateur du nœud observateur a redémarré, l’étape suivante consiste à exécuter le Watchernode.msi de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d2bef-123">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="d2bef-124">Pour exécuter ce fichier, ouvrez Lync Server 2013 Management Shell en cliquant sur **Démarrer**, sur **tous les programmes**, sur **Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2bef-124">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="d2bef-125">Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée (Assurez-vous et spécifiez le chemin d’accès réel à votre copie de Watchernode.msi) :</span><span class="sxs-lookup"><span data-stu-id="d2bef-125">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="d2bef-p104">Comme indiqué précédemment, vous pouvez également exécuter Watchernode.msi à partir d’une fenêtre de commande. Pour ouvrir une fenêtre de commande, cliquez sur <STRONG>Démarrer</STRONG>, cliquez avec le bouton droit sur <STRONG>Invite de commandes</STRONG>, puis cliquez sur <STRONG>Exécuter en tant qu’administrateur</STRONG>. Lorsque la fenêtre de commande s’ouvre, tapez la même commande que précédemment.</span><span class="sxs-lookup"><span data-stu-id="d2bef-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="d2bef-129">Le mode Négocier est utilisé à chaque fois que le nœud observateur ne peut pas être configuré en tant que pool d’application approuvées.</span><span class="sxs-lookup"><span data-stu-id="d2bef-129">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="d2bef-130">Dans ce mode, les administrateurs devront gérer les mots de passe des utilisateurs de test sur le nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="d2bef-130">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

