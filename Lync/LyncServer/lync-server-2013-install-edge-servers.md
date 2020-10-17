---
title: 'Lync Server 2013 : installation des serveurs Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81a17eacb30c62f64185508afef3842408238ba4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498741"
---
# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="7bb26-102">Installer des serveurs Edge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bb26-102">Install Edge Servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bb26-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7bb26-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="7bb26-104">Vous installez Lync Server 2013 sur des serveurs Edge à l’aide de l’Assistant Déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7bb26-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="7bb26-105">En exécutant l’Assistant Déploiement sur chaque serveur Edge, vous pouvez effectuer la plupart des tâches requises pour configurer le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7bb26-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="7bb26-106">Pour déployer Lync Server 2013 sur un serveur Edge, vous devez déjà exécuter le générateur de topologie pour définir et publier votre topologie de serveur Edge, puis l’exporter vers le média disponible à partir du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7bb26-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="7bb26-107">Pour plus d’informations, reportez-vous à la rubrique [scénarios pour l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) et [exportation de votre topologie Lync Server 2013 et copiez-la sur des médias externes pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="7bb26-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="7bb26-108">Après avoir utilisé l’Assistant déploiement pour installer chaque serveur Edge, installer et affecter les certificats requis, et démarrer les services requis, vous pouvez effectuer l’installation en utilisant les informations de la procédure de configuration de la [prise en charge de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) pour activer et configurer l’accès des utilisateurs externes et les informations de [vérification de votre déploiement Edge dans 2013 Lync](lync-server-2013-verifying-your-edge-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="7bb26-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="7bb26-109">Pour installer un serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7bb26-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="7bb26-110">Ouvrez une session sur l’ordinateur sur lequel vous souhaitez installer le serveur Edge en tant que membre du groupe Administrateurs local ou avec un compte disposant de droits et d’autorisations équivalents.</span><span class="sxs-lookup"><span data-stu-id="7bb26-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="7bb26-111">Assurez-vous que le fichier de configuration de topologie que vous avez créé à l’aide du générateur de topologie, puis exporté et copié vers le support externe, est disponible sur le serveur de périphérie (par exemple, l’accès au lecteur USB sur lequel vous avez copié le fichier de configuration de topologie ou vérifiez l’accès au partage réseau où vous avez copié le fichier).</span><span class="sxs-lookup"><span data-stu-id="7bb26-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="7bb26-112">Démarrez l’Assistant Déploiement.</span><span class="sxs-lookup"><span data-stu-id="7bb26-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7bb26-p102">Si vous obtenez un message vous indiquant que vous devez installer Microsoft Visual C++ Redistributable, cliquez sur <STRONG>Oui</STRONG>. Dans la boîte de dialogue suivante, acceptez l’<STRONG>emplacement d’installation</STRONG> par défaut ou cliquez sur <STRONG>Parcourir</STRONG> pour sélectionner un autre emplacement, puis cliquez sur <STRONG>Installer</STRONG>. Dans la boîte de dialogue suivante, activez la case à cocher <STRONG>J’accepte les termes du contrat de licence</STRONG>, puis cliquez sur <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7bb26-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="7bb26-116">Dans l’Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7bb26-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="7bb26-117">Une fois que l’Assistant a déterminé l’état du déploiement, pour **Étape 1. Installer le magasin de configurations local**, cliquez sur **Exécuter**, puis effectuez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="7bb26-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="7bb26-118">Dans la boîte de dialogue **Configurer le réplica local du magasin central de gestion**, cliquez sur **Importer à partir d’un fichier (recommandé pour les serveurs Edge)**, accédez à l’emplacement du fichier de configuration de la topologie exporté, sélectionnez le fichier .zip, cliquez sur **Ouvrir**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7bb26-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="7bb26-119">L’Assistant Déploiement lit les informations de configuration du fichier de configuration et écrit le fichier de configuration XML sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="7bb26-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="7bb26-120">Une fois que le processus **Exécution de commandes** est terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="7bb26-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="7bb26-121">Dans l’Assistant Déploiement, cliquez sur **étape 2 : installer ou supprimer des composants Lync Server** pour installer les composants de serveur Edge lync Server 2013 spécifiés dans le fichier de configuration XML qui est stocké sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="7bb26-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="7bb26-122">Une fois l’installation terminée, utilisez les informations de [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) pour installer et affecter les certificats requis avant de démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="7bb26-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

