---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actuels.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814702"
---
# <a name="tbladcookie"></a><span data-ttu-id="2a172-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="2a172-103">tblADCookie</span></span>
 
<span data-ttu-id="2a172-104">tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actuels.</span><span class="sxs-lookup"><span data-stu-id="2a172-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="2a172-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="2a172-105">**Columns**</span></span>

|<span data-ttu-id="2a172-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2a172-106">**Column**</span></span>|<span data-ttu-id="2a172-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="2a172-107">**Type**</span></span>|<span data-ttu-id="2a172-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="2a172-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a172-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2a172-109">prinGuid</span></span>  <br/> |<span data-ttu-id="2a172-110">GUID, pas null</span><span class="sxs-lookup"><span data-stu-id="2a172-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="2a172-111">GUID principal du domaine qui est surveillé.</span><span class="sxs-lookup"><span data-stu-id="2a172-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="2a172-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="2a172-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="2a172-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="2a172-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="2a172-114">Nom de domaine complet (FQDN) du contrôleur de domaine actuel utilisé pour la synchronisation des services de domaine Active Directory (AD DS). A une valeur d’information.</span><span class="sxs-lookup"><span data-stu-id="2a172-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="2a172-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="2a172-115">adcContent</span></span>  <br/> |<span data-ttu-id="2a172-116">image (binaire)</span><span class="sxs-lookup"><span data-stu-id="2a172-116">image (binary)</span></span>  <br/> |<span data-ttu-id="2a172-117">Cookie de synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a172-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="2a172-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2a172-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="2a172-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2a172-119">datetime</span></span>  <br/> |<span data-ttu-id="2a172-120">Date et heure de la mise à jour de ligne.</span><span class="sxs-lookup"><span data-stu-id="2a172-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="2a172-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="2a172-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="2a172-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2a172-122">datetime</span></span>  <br/> |<span data-ttu-id="2a172-123">Temps nécessaire au verrouillage de la ligne pour les modifications.</span><span class="sxs-lookup"><span data-stu-id="2a172-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="2a172-124">Il s’agit d’une partie d’un mécanisme de verrouillage de logiciels qui garantit que seul l’un des services de chat effectue la synchronisation Active Directory à la fois.</span><span class="sxs-lookup"><span data-stu-id="2a172-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="2a172-125">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="2a172-125">**Keys**</span></span>

|<span data-ttu-id="2a172-126">**Colonne (s)**</span><span class="sxs-lookup"><span data-stu-id="2a172-126">**Column(s)**</span></span>|<span data-ttu-id="2a172-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="2a172-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a172-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2a172-128">prinGuid</span></span>  <br/> |<span data-ttu-id="2a172-129">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="2a172-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2a172-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2a172-130">prinGuid</span></span>  <br/> |<span data-ttu-id="2a172-131">Clé étrangère avec recherche dans la table principale. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="2a172-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

