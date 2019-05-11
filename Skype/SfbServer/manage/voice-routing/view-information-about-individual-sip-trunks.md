---
title: Afficher des informations sur les jonctions SIP individuelles dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans Skype pour Business Server, vous pouvant assigner plusieurs jonctions à une seule passerelle PSTN ; Cela signifie que les passerelles et les jonctions ne sont pas les mêmes, et les administrateurs doivent utiliser l’applet de commande Get-CsTrunk pour afficher des informations sur une jonction SIP individuelle.
ms.openlocfilehash: bf9229dba17b7b2e49eb9a05d9469f42c0b9b998
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930819"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="83ec8-103">Afficher des informations sur les jonctions SIP individuelles dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="83ec8-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="83ec8-104">Dans Skype pour Business Server, vous pouvant assigner plusieurs jonctions à une seule passerelle PSTN ; Cela signifie que les passerelles et jonctions ne sont pas les mêmes, et que les administrateurs doivent utiliser l’applet de commande [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur une jonction SIP individuelle.</span><span class="sxs-lookup"><span data-stu-id="83ec8-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="83ec8-105">L’applet de commande Get-CsTrunk peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83ec8-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="83ec8-106">**Pour afficher des informations sur toutes vos jonctions SIP**</span><span class="sxs-lookup"><span data-stu-id="83ec8-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="83ec8-107">La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="83ec8-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="83ec8-108">**Pour afficher les informations relatives à une jonction SIP spécifique**</span><span class="sxs-lookup"><span data-stu-id="83ec8-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="83ec8-109">La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="83ec8-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="83ec8-110">**Affichage des informations pour toutes les jonctions SIP affectées à un Pool**</span><span class="sxs-lookup"><span data-stu-id="83ec8-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="83ec8-111">Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :</span><span class="sxs-lookup"><span data-stu-id="83ec8-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
