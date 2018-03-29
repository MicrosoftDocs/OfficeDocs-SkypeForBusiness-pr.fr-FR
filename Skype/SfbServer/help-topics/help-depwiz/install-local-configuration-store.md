---
title: Installer le magasin de configurations local
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Pour commencer l’installation d’un nouveau Skype pour serveur de rôle 2015 de serveur d’entreprise, vous devez d’abord installer le SQL Server local qui héberge la banque de configuration local. Le magasin de configuration local agit comme un réplica en lecture seule de la Skype pour la banque de gestion Central Server (CMS). Vous devez être connecté au serveur de sont en cours d’exécution l’étape d’installation Local Configuration magasin en tant qu’administrateur local sur l’ordinateur et l’appartenance à la RTCUniversalServerAdmins ou le groupe RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologies est lu à partir du document de définition exportée plutôt qu’à partir du magasin Central de gestion. Pour exporter le document de définition du Générateur de topologies et le rendre disponible pour les serveurs Edge, consultez la rubrique Exporter de votre topologie et copie il sur un support externe pour l’Installation de bord.
ms.openlocfilehash: adce98e053b6959c3513885fc53f1616df1c1125
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="996b2-108">Installer le magasin de configurations local</span><span class="sxs-lookup"><span data-stu-id="996b2-108">Install Local Configuration Store</span></span>
 
<span data-ttu-id="996b2-109">Pour commencer l’installation d’un nouveau Skype pour serveur de rôle 2015 de serveur d’entreprise, vous devez d’abord installer le SQL Server local qui héberge la banque de configuration local.</span><span class="sxs-lookup"><span data-stu-id="996b2-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="996b2-110">Le magasin de configuration local agit comme un réplica en lecture seule de la Skype pour la banque de gestion Central Server (CMS).</span><span class="sxs-lookup"><span data-stu-id="996b2-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="996b2-111">Vous devez être connecté au serveur décrit à l’étape **Installer le magasin de configurations local** en tant qu’administrateur local de l’ordinateur ; en outre, vous devez être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="996b2-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="996b2-112">Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="996b2-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="996b2-113">Le document de définition du Générateur de topologies est lu à partir du document de définition exportée plutôt qu’à partir du magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="996b2-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="996b2-114">Pour exporter le document de définition du Générateur de topologies et le rendre disponible pour les serveurs Edge, reportez-vous à la rubrique[exportation de votre topologie et copie sur un support externe pour l’Installation de bord](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="996b2-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>
  
<span data-ttu-id="996b2-115">Pour commencer l’installation :</span><span class="sxs-lookup"><span data-stu-id="996b2-115">To begin the installation:</span></span>
  
1. <span data-ttu-id="996b2-116">Sur le Skype pour Business Server 2015, page, à côté **étape 1 : magasin de Configuration Local Installation**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="996b2-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>
    
2. <span data-ttu-id="996b2-117">Dans la page **Configuration du serveur local** assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="996b2-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>
    
3. <span data-ttu-id="996b2-118">Une fois l’installation terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="996b2-118">When the local server configuration installation is complete, click **Finish**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="996b2-119">L’installation de la locale de SQL Server peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="996b2-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="996b2-120">Vous ne verrez pas les mises à jour de progression dans l’écran Résumé d’installation pendant l’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="996b2-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="996b2-121">Si vous voulez surveiller la progression de l’installation, utilisez le Gestionnaire des tâches pour surveiller le programme d’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="996b2-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span> 
  

