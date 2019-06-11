---
title: 'Lync Server 2013: installer les fichiers pour le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="99993-102">Installer les fichiers pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99993-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99993-103">_**Dernière modification de la rubrique:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="99993-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="99993-104">Pour mener à bien cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine appartenant au moins au groupe RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="99993-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="99993-105">Suivez les étapes décrites dans cette rubrique pour exécuter l’Assistant Déploiement de Lync Server 2013 et installer les fichiers pour le serveur de médiation sur un ordinateur que vous avez ajouté à un pool de serveurs de médiation lorsque vous avez utilisé le générateur de topologie pour définir et publier le pool.</span><span class="sxs-lookup"><span data-stu-id="99993-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="99993-106">Lors de l’installation de files Mediation Server, vous installez et attribuez également le certificat requis par chaque ordinateur d’un pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="99993-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="99993-107">Sur ce site, si vous avez déjà déployé des serveurs de médiation colocalisés sur les pools frontaux ou le serveur Standard Edition Server, vous pouvez ignorer cette rubrique et, à la place, continuer à [configurer les Trunks dans Lync server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="99993-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99993-108">Cette rubrique part du principe que vous avez déjà défini et publié un pool de serveurs de médiation autonome comme décrit dans la rubrique <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">définir un serveur de médiation dans le générateur de topologie de Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publier la topologie dans Lync Server 2013</A> dans le déploiement. et que vous avez vérifié que les ordinateurs figurant dans le pool de serveurs de médiation répondent aux conditions préalables décrites dans la rubrique <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">logiciels requis pour Enterprise Voice dans Lync Server 2013</A> et la <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Configuration requise pour Voix entreprise dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99993-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="99993-109">Pour installer les fichiers sur un pool de serveurs de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="99993-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="99993-110">À partir du support d’installation, cliquez \<avec le\>bouton droit sur installation Media**\\Setup\\. exe amd64\\**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="99993-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="99993-111">Dans la page **Emplacement d’installation**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99993-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="99993-p102">Dans la page **Contrat de Licence Utilisateur Final**, cliquez sur **J’accepte**, puis sur **OK**. (Cette étape est nécessaire pour continuer.)</span><span class="sxs-lookup"><span data-stu-id="99993-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>

4.  <span data-ttu-id="99993-114">Dans la page **Assistant Déploiement de Lync Server 2010** , cliquez sur **installer ou mettre à jour le système de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="99993-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="99993-115">Lors de l’**étape 1 : installation du magasin de configuration local**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="99993-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="99993-116">Dans la page **Configurer un réplica local du magasin central de gestion**, acceptez le paramètre par défaut **Récupérer directement à partir du magasin central de gestion**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="99993-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="99993-117">Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="99993-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="99993-118">À côté de l' **étape 2: installer ou supprimer les composants Lync Server**, cliquez sur **exécuter**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="99993-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="99993-119">Dans la page **Exécution de commandes**, lorsque le statut de la tâche est **Terminé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="99993-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="99993-p103">Lors de l’**étape 3 : demande, installation et affectation des certificats**, cliquez sur **Exécuter**. Suivez les instructions qui s’affichent à l’écran, en acceptant les paramètres par défaut. Le serveur de médiation nécessite un certificat. Vous devrez donc répéter deux fois l’**étape 3** : une fois pour émettre le certificat nécessaire, une autre pour l’affecter.</span><span class="sxs-lookup"><span data-stu-id="99993-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="99993-123">Une fois le certificat émis et attribué lors de l’**étape 4: démarrage des services**, cliquez sur **Exécuter**, puis suivez les instructions affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="99993-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="99993-124">Une fois l’**étape 4** terminée, redémarrez le serveur et connectez-vous y en tant que membre du groupe DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="99993-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="99993-125">Sur l’ordinateur sur lequel vous exécutez le panneau de configuration de Lync Server, vérifiez sur la page **Topology** du panneau de configuration de Lync Server que l’état du service du serveur de médiation est représenté par une coche verte.</span><span class="sxs-lookup"><span data-stu-id="99993-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="99993-126">Si une croix rouge est affichée, sélectionnez le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="99993-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="99993-127">Dans le menu **Action**, cliquez sur **Démarrer tous les services**.</span><span class="sxs-lookup"><span data-stu-id="99993-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="99993-128">Si vous avez ajouté plusieurs ordinateurs au pool de serveurs de médiation, suivez les étapes de cette procédure sur tous les autres ordinateurs du pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="99993-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="99993-129">Si vous n’avez pas besoin d’installer des fichiers pour un serveur de médiation pour d’autres ordinateurs, suivez les procédures décrites dans la section [configuration de Trunks dans Lync server 2013](lync-server-2013-configuring-trunks.md) pour configurer les paramètres de la connexion de Trunk entre ce pool de serveurs de médiation (ou toute la médiation Serveurs sur un site) et son homologue.</span><span class="sxs-lookup"><span data-stu-id="99993-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99993-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99993-130">See Also</span></span>


[<span data-ttu-id="99993-131">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99993-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

