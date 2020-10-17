---
title: Supprimer une entrée d’hôte autorisé
description: Supprimer une entrée d’hôte autorisé.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95aa8df1745ad3108654fcb9b441b5919d42ec40
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570280"
---
# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="3ed42-103">Supprimer une entrée d’hôte autorisé</span><span class="sxs-lookup"><span data-stu-id="3ed42-103">Remove an authorized host entry</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ed42-104">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="3ed42-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="3ed42-105">Cette rubrique explique comment supprimer une entrée d’hôte autorisé héritée (connue sous le nom d' *entrée d’application approuvée* dans Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="3ed42-105">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="3ed42-106">Vous devez supprimer les entrées d’hôte autorisé existantes pour toutes les passerelles SIP/CSTA dans votre déploiement Office Communications Server 2007 R2 lorsque vous migrez le contrôle d’appel distant vers un déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ed42-106">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="3ed42-107">Vous devez utiliser les outils d’administration inclus dans Office Communications Server 2007 R2 pour supprimer les entrées existantes de l’hôte autorisé.</span><span class="sxs-lookup"><span data-stu-id="3ed42-107">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="3ed42-108">Pour supprimer une entrée d’hôte autorisé dans un déploiement d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3ed42-108">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="3ed42-109">Ouvrez la console d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3ed42-109">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="3ed42-110">Développez l’arborescence et cliquez avec le bouton droit sur le pool dans lequel l’hôte autorisé a été créé.</span><span class="sxs-lookup"><span data-stu-id="3ed42-110">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="3ed42-111">Cliquez sur **Propriétés**, puis sur **Propriétés du serveur frontal**.</span><span class="sxs-lookup"><span data-stu-id="3ed42-111">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="3ed42-112">Cliquez sur l’onglet **Autorisation de l’hôte**.</span><span class="sxs-lookup"><span data-stu-id="3ed42-112">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="3ed42-113">Sélectionnez un serveur, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="3ed42-113">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="3ed42-114">Dans **Propriétés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ed42-114">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

