---
title: Afficher des informations sur les circuits SIP individuels dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans Skype entreprise Server, plusieurs Trunks peuvent être affectées à une seule passerelle RTC; Cela signifie que les passerelles et les Trunks ne sont pas les mêmes et qu’ils doivent utiliser l’applet de cmdlet Get-CsTrunk pour afficher des informations sur un Trunk SIP individuel.
ms.openlocfilehash: f9199936dd4c9580c95c8b9708df04dcac13e1e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274876"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="68889-103">Afficher des informations sur les circuits SIP individuels dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="68889-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="68889-104">Dans Skype entreprise Server, plusieurs Trunks peuvent être affectées à une seule passerelle RTC; Cela signifie que les passerelles et les Trunks ne sont pas les mêmes que les passerelles et les administrateurs doivent utiliser l’applet de passe [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur un Trunk SIP individuel.</span><span class="sxs-lookup"><span data-stu-id="68889-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="68889-105">Vous pouvez exécuter l’applet de commande Get-CsTrunk à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68889-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="68889-106">**Pour afficher des informations sur toutes vos jonctions SIP**</span><span class="sxs-lookup"><span data-stu-id="68889-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="68889-107">La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="68889-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="68889-108">**Pour afficher les informations relatives à une jonction SIP spécifique**</span><span class="sxs-lookup"><span data-stu-id="68889-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="68889-109">La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="68889-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="68889-110">**Affichage des informations pour toutes les lignes SIP attribuées à un pool**</span><span class="sxs-lookup"><span data-stu-id="68889-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="68889-111">Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :</span><span class="sxs-lookup"><span data-stu-id="68889-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
