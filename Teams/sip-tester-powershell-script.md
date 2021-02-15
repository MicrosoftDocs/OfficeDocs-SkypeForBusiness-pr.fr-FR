---
title: Script PowerShell de test des connexions du contrôleur de bordure de session de routage direct
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Utilisez cet exemple de script PowerShell pour tester les connexions du contrôleur de bordure de session de routage direct dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834274"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="01d33-103">Script PowerShell de test des connexions du contrôleur de bordure de session de routage direct</span><span class="sxs-lookup"><span data-stu-id="01d33-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="01d33-104">Le client de test SIP est un exemple de script PowerShell que vous pouvez utiliser pour tester les connexions du contrôleur de bordure de session de routage direct (SBC) dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="01d33-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="01d33-105">Ce script teste la fonctionnalité de base d’une ligne SIP (Session Initiation Protocol) couplée au client avec le routage direct.</span><span class="sxs-lookup"><span data-stu-id="01d33-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="01d33-106">Le script envoie un test SIP au deuxième résultat, attend le résultat, puis le présente dans un format lisible par l’homme.</span><span class="sxs-lookup"><span data-stu-id="01d33-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="01d33-107">Vous pouvez utiliser ce script pour tester les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="01d33-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="01d33-108">Appels sortants et entrants</span><span class="sxs-lookup"><span data-stu-id="01d33-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="01d33-109">Sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="01d33-109">Simultaneous ring</span></span>
- <span data-ttu-id="01d33-110">Escalade multimédia</span><span class="sxs-lookup"><span data-stu-id="01d33-110">Media escalation</span></span>
- <span data-ttu-id="01d33-111">Transfert consultatif</span><span class="sxs-lookup"><span data-stu-id="01d33-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="01d33-112">Télécharger le script et la documentation</span><span class="sxs-lookup"><span data-stu-id="01d33-112">Download the script and documentation</span></span>

<span data-ttu-id="01d33-113">Téléchargez le script client et la documentation du [test SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="01d33-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="01d33-114">Le script client de test SIP prend adal.ps uniquement en charge la version 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="01d33-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="01d33-115">Une erreur est renvoyée si une version ultérieure du adal.ps est utilisée.</span><span class="sxs-lookup"><span data-stu-id="01d33-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
