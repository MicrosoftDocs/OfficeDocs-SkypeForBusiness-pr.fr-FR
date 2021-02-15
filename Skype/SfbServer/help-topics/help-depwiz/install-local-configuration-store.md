---
title: Installer le magasin de configurations local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Pour commencer l’installation d’un nouveau serveur de rôles Skype Entreprise Server 2015, vous devez d’abord installer le SQL Server local qui hébergera le magasin de configurations local. Le magasin de configurations local agit comme un réplica en lecture seule du magasin central de gestion (CMS) de Skype Entreprise Server. Vous devez être connecté en tant qu’administrateur local sur le serveur sur lequel vous exécutez l’étape Installer le magasin de configurations local, et être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur de périphérie, il n’est pas nécessaire que vous soyez membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologie sera lu à partir du document de définition exporté et non du magasin central de gestion. Pour exporter le document de définition du Générateur de topologie et le rendre disponible pour les serveurs Edge, consultez la rubrique Exporter votre topologie et la copier sur un support externe pour l’installation Edge.
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827144"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="7af6d-108">Installer le magasin de configurations local</span><span class="sxs-lookup"><span data-stu-id="7af6d-108">Install Local Configuration Store</span></span>

<span data-ttu-id="7af6d-109">Pour commencer l’installation d’un nouveau serveur de rôles Skype Entreprise Server 2015, vous devez d’abord installer le SQL Server local qui hébergera le magasin de configurations local.</span><span class="sxs-lookup"><span data-stu-id="7af6d-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="7af6d-110">Le magasin de configurations local agit comme un réplica en lecture seule du magasin central de gestion (CMS) de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7af6d-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="7af6d-111">Vous devez être connecté en tant qu’administrateur local sur le serveur sur lequel vous exécutez l’étape **Installer le magasin de configurations local**, et être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="7af6d-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="7af6d-112">Si vous effectuez l’installation sur un serveur de périphérie, il n’est pas nécessaire que vous soyez membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="7af6d-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="7af6d-113">Le document de définition du Générateur de topologie sera lu à partir du document de définition exporté et non du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="7af6d-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="7af6d-114">Pour exporter le document de définition du Générateur de topologie et le rendre disponible pour les serveurs Edge, consultez la rubrique Exporter votre topologie et la copier sur un support externe pour [l’installation Edge.](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)</span><span class="sxs-lookup"><span data-stu-id="7af6d-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="7af6d-115">Pour commencer l’installation :</span><span class="sxs-lookup"><span data-stu-id="7af6d-115">To begin the installation:</span></span>

1. <span data-ttu-id="7af6d-116">Dans la page Skype Entreprise Server 2015, à côté de l’étape 1 : Installer le magasin **de configurations local,** cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7af6d-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="7af6d-117">Dans la page **Configuration du serveur local**, assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7af6d-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="7af6d-118">Une fois l’installation terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="7af6d-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="7af6d-119">L’installation du SQL Server local peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="7af6d-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="7af6d-120">Les mises à jour de la progression ne s’afficheront pas dans l’écran récapitulatif de l’installation pendant SQL Server’installation.</span><span class="sxs-lookup"><span data-stu-id="7af6d-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="7af6d-121">Si vous souhaitez surveiller la progression de l’installation, utilisez le Gestionnaire des tâches pour surveiller SQL Server configuration.</span><span class="sxs-lookup"><span data-stu-id="7af6d-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


