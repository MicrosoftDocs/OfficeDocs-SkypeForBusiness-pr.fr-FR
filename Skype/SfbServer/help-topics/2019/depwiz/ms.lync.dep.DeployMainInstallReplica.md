---
title: Installer le magasin de configurations local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation d’un nouveau serveur de rôles Skype entreprise Server, vous devez d’abord installer le serveur SQL Server local qui hébergera le magasin de configuration local. Le magasin de configuration local fera office de réplica en lecture seule du magasin de gestion centralisé de Skype entreprise Server (CMS).
ms.openlocfilehash: 365529c3c9cb15ea50cd6a482bd2a69143daa219
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794793"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="cf6d7-104">Installer le magasin de configurations local</span><span class="sxs-lookup"><span data-stu-id="cf6d7-104">Install Local Configuration Store</span></span>

<span data-ttu-id="cf6d7-105">Pour commencer l’installation d’un nouveau serveur de rôles Skype entreprise Server, vous devez d’abord installer le serveur SQL Server local qui hébergera le magasin de configuration local.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="cf6d7-106">Le magasin de configuration local fera office de réplica en lecture seule du magasin de gestion centralisé de Skype entreprise Server (CMS).</span><span class="sxs-lookup"><span data-stu-id="cf6d7-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="cf6d7-107">Vous devez être connecté au serveur décrit à l’étape **Installer le magasin de configurations local** en tant qu’administrateur local de l’ordinateur ; en outre, vous devez être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="cf6d7-108">Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="cf6d7-109">Le document de définition du générateur de topologie sera lu à partir du document de définition exporté plutôt que du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="cf6d7-110">Pour exporter le document de définition du générateur de topologie et le mettre à la disposition des serveurs de périphérie, voir la rubrique[exporter votre topologie et copier celle-ci sur des éléments multimédias externes pour l’installation Edge](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf6d7-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="cf6d7-111">Pour commencer l’installation :</span><span class="sxs-lookup"><span data-stu-id="cf6d7-111">To begin the installation:</span></span>

1. <span data-ttu-id="cf6d7-112">Dans la page Skype entreprise Server, en regard de la page **étape suivante : installer le magasin de configuration local**, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="cf6d7-113">Dans la page **Configuration du serveur local** assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="cf6d7-114">Une fois l’installation terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="cf6d7-115">L’installation du serveur local SQL Server peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="cf6d7-116">Vous ne verrez pas les mises à jour en cours dans l’écran Résumé de l’installation lors de l’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="cf6d7-117">Si vous souhaitez surveiller la progression de l’installation, utilisez le gestionnaire des tâches pour consulter la configuration de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cf6d7-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


