---
title: Script PowerShell pour tester les connexions du contrôleur de bordure de session de routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Utilisez cet exemple de script PowerShell pour tester les connexions du contrôleur de bordereaux de routage direct dans Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568676"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="26875-103">Script PowerShell pour tester les connexions du contrôleur de bordure de session de routage direct</span><span class="sxs-lookup"><span data-stu-id="26875-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="26875-104">Le client du testeur SIP est un exemple de script PowerShell que vous pouvez utiliser pour tester les connexions de contrôleur de session de routage direct (SBC) dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="26875-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="26875-105">Ce script teste les fonctionnalités de base d’un Trunk SIP (Session Initiation Protocol) avec le routage direct.</span><span class="sxs-lookup"><span data-stu-id="26875-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="26875-106">Le script envoie un test SIP au testeur de tests, attend le résultat, puis le présente dans un format lisible par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="26875-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="26875-107">Vous pouvez utiliser ce script pour tester les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="26875-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="26875-108">Appels sortants et entrants</span><span class="sxs-lookup"><span data-stu-id="26875-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="26875-109">Sonnerie simultanée</span><span class="sxs-lookup"><span data-stu-id="26875-109">Simultaneous ring</span></span>
- <span data-ttu-id="26875-110">Réaffectation de médias</span><span class="sxs-lookup"><span data-stu-id="26875-110">Media escalation</span></span>
- <span data-ttu-id="26875-111">Transfert de consultation</span><span class="sxs-lookup"><span data-stu-id="26875-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="26875-112">Télécharger le script et la documentation</span><span class="sxs-lookup"><span data-stu-id="26875-112">Download the script and documentation</span></span>

<span data-ttu-id="26875-113">Téléchargez le [script et la documentation client du testeur SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="26875-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>