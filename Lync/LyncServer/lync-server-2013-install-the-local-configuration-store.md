---
title: 'Lync Server 2013 : Installation du magasin de configurations local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="65b38-102">Installation du magasin de configurations local dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65b38-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65b38-103">_**Dernière modification de la rubrique :** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="65b38-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="65b38-104">Avant de procéder à ces étapes, assurez-vous que vous êtes connecté au serveur à l’aide d’un compte d’utilisateur de domaine qui est un administrateur local et un membre du groupe RTCUniversalReadOnlyAdmin.</span><span class="sxs-lookup"><span data-stu-id="65b38-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="65b38-105">Pour pouvoir utiliser l’Assistant Déploiement de Lync Server, le magasin de configuration local doit exister sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="65b38-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="65b38-106">Le magasin de configuration local est une copie en lecture seule du magasin de gestion central, qui est créée après l’installation locale de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="65b38-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="65b38-107">Le magasin de gestion central proprement dit est ajouté à la base de données SQL Server existante qui est installé sur la base de données SQL Server Standard Server ou SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="65b38-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="65b38-108">Si vous n’avez pas encore exécuté le programme d’installation de Lync Server 2013 sur ce serveur, vous serez invité à entrer un lecteur et un chemin d’accès pour installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65b38-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="65b38-109">Cela vous permettra de procéder à l’installation sur un lecteur autre que le lecteur système, si votre organisation l’exige, ou si vous avez des problèmes d’espace.</span><span class="sxs-lookup"><span data-stu-id="65b38-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="65b38-110">Dans la boîte de dialogue d’installation, il vous suffit de changer le chemin d’accès d’installation pour les fichiers du serveur Lync vers un nouveau lecteur disponible.</span><span class="sxs-lookup"><span data-stu-id="65b38-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="65b38-111">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, le reste des fichiers Lync Server 2013 y sera également déployé.</span><span class="sxs-lookup"><span data-stu-id="65b38-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="65b38-112">Pour installer le magasin de configuration local</span><span class="sxs-lookup"><span data-stu-id="65b38-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="65b38-113">À partir de votre support d’installation \\,\\accédez\\à Setup. exe. exe, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b38-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="65b38-114">Si vous êtes invité à installer Microsoft Visual C++ 2012 redistribuable, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="65b38-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="65b38-115">Dans la page de l’emplacement de l' **installation de Lync Server 2013** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b38-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="65b38-116">Sur la page **contrat de licence utilisateur final** , passez en revue les termes du contrat de licence, vous devez sélectionner **J’accepte les conditions du contrat de licence**, puis cliquez sur **OK** pour pouvoir continuer.</span><span class="sxs-lookup"><span data-stu-id="65b38-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="65b38-117">Dans la page de l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système serveur Lync**.</span><span class="sxs-lookup"><span data-stu-id="65b38-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="65b38-118">Sur la page **Lync Server 2013** , à côté de la page **étape suivante : installer le magasin de configuration local**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="65b38-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="65b38-119">Dans la page **Installer le magasin de configurations local**, assurez-vous que l’option **Récupérer directement à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="65b38-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="65b38-120">Lorsque l’installation de configuration du serveur local est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="65b38-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

