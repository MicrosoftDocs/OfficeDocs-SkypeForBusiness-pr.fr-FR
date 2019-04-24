---
title: Boîtes de dialogue tableau Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La table Dialogs est une table de prise en charge qui stocke les informations sur le Dialogid pour les sessions d’égal à égal.
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213654"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4b7da-103">Boîtes de dialogue tableau Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b7da-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4b7da-104">La table Dialogs est une table de prise en charge qui stocke les informations sur le Dialogid pour les sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4b7da-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="4b7da-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4b7da-105">**Column**</span></span>|<span data-ttu-id="4b7da-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="4b7da-106">**Data Type**</span></span>|<span data-ttu-id="4b7da-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="4b7da-107">**Key/Index**</span></span>|<span data-ttu-id="4b7da-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="4b7da-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b7da-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="4b7da-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="4b7da-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="4b7da-110">datetime</span></span>  <br/> |<span data-ttu-id="4b7da-111">Principal</span><span class="sxs-lookup"><span data-stu-id="4b7da-111">Primary</span></span>  <br/> |<span data-ttu-id="4b7da-112">Heure de la demande de session ; utilisé en conjonction avec SessionIDSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="4b7da-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="4b7da-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="4b7da-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="4b7da-114">int</span><span class="sxs-lookup"><span data-stu-id="4b7da-114">int</span></span>  <br/> |<span data-ttu-id="4b7da-115">Principal</span><span class="sxs-lookup"><span data-stu-id="4b7da-115">Primary</span></span>  <br/> |<span data-ttu-id="4b7da-116">Numéro d’identification pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="4b7da-116">ID number to identify the session.</span></span> <span data-ttu-id="4b7da-117">Utilisé conjointement avec SessionIDTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="4b7da-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="4b7da-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="4b7da-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="4b7da-119">int</span><span class="sxs-lookup"><span data-stu-id="4b7da-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="4b7da-120">Somme de contrôle de la ExternalID.</span><span class="sxs-lookup"><span data-stu-id="4b7da-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="4b7da-121">Ce champ est utilisé pour augmenter la vitesse des recherches de base de données.</span><span class="sxs-lookup"><span data-stu-id="4b7da-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="4b7da-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="4b7da-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="4b7da-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="4b7da-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="4b7da-124">ID de boîte de dialogue SIP, stockée sous forme d’un fichier binaire.</span><span class="sxs-lookup"><span data-stu-id="4b7da-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="4b7da-125">Le format de fichier binaire est :</span><span class="sxs-lookup"><span data-stu-id="4b7da-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="4b7da-126">boîte de dialogue de balise ; pour une balise</span><span class="sxs-lookup"><span data-stu-id="4b7da-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="4b7da-127">Ces données peuvent être converties au format texte à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="4b7da-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

