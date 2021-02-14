---
title: Table Dialogs in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La table Dialogs est une table de prise en charge qui stocke les informations sur les DialogIDs pour les sessions d’égal à égal.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816044"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8ae94-103">Table Dialogs in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8ae94-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8ae94-104">La table Dialogs est une table de prise en charge qui stocke les informations sur les DialogIDs pour les sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="8ae94-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="8ae94-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8ae94-105">**Column**</span></span>|<span data-ttu-id="8ae94-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="8ae94-106">**Data Type**</span></span>|<span data-ttu-id="8ae94-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="8ae94-107">**Key/Index**</span></span>|<span data-ttu-id="8ae94-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="8ae94-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ae94-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="8ae94-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="8ae94-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8ae94-110">datetime</span></span>  <br/> |<span data-ttu-id="8ae94-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="8ae94-111">Primary</span></span>  <br/> |<span data-ttu-id="8ae94-112">Heure de la demande de session ; utilisé conjointement avec SessionIDSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="8ae94-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="8ae94-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="8ae94-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="8ae94-114">int</span><span class="sxs-lookup"><span data-stu-id="8ae94-114">int</span></span>  <br/> |<span data-ttu-id="8ae94-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="8ae94-115">Primary</span></span>  <br/> |<span data-ttu-id="8ae94-116">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="8ae94-116">ID number to identify the session.</span></span> <span data-ttu-id="8ae94-117">Utilisé conjointement avec SessionIDTime pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="8ae94-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="8ae94-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="8ae94-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="8ae94-119">int</span><span class="sxs-lookup"><span data-stu-id="8ae94-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="8ae94-120">Checksum de l’ExternalID.</span><span class="sxs-lookup"><span data-stu-id="8ae94-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="8ae94-121">Ce champ est utilisé pour augmenter la vitesse des recherches dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="8ae94-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="8ae94-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="8ae94-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="8ae94-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="8ae94-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="8ae94-124">ID de boîte de dialogue SIP, stocké en tant que fichier binaire.</span><span class="sxs-lookup"><span data-stu-id="8ae94-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="8ae94-125">Le format du fichier binaire est :</span><span class="sxs-lookup"><span data-stu-id="8ae94-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="8ae94-126">dialog;from-tag;to-tag</span><span class="sxs-lookup"><span data-stu-id="8ae94-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="8ae94-127">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="8ae94-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

