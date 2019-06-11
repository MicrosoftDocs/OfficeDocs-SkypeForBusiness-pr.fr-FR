---
title: Supprimer une entrée d’hôte autorisée
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca9bc99382e904c398dbb7434b2ee6343ab661ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="b5a1b-102">Supprimer une entrée d’hôte autorisée</span><span class="sxs-lookup"><span data-stu-id="b5a1b-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5a1b-103">_**Dernière modification de la rubrique:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="b5a1b-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="b5a1b-104">Cette rubrique explique comment supprimer une entrée d’hôte autorisé héritée (connue sous le nom d' *entrée d’application fiable* dans Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="b5a1b-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="b5a1b-105">Vous devez supprimer les entrées d’hôte autorisées existantes pour toutes les passerelles SIP/CSTA dans votre déploiement d’Office Communications Server 2007 R2 lors de la migration du contrôle d’appel distant vers un déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5a1b-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="b5a1b-106">Vous devez utiliser les outils d’administration inclus dans Office Communications Server 2007 R2 pour supprimer les entrées d’hébergement autorisées existantes.</span><span class="sxs-lookup"><span data-stu-id="b5a1b-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="b5a1b-107">Pour supprimer une entrée d’hôte autorisée dans un déploiement d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b5a1b-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="b5a1b-108">Ouvrez la console d’administration d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b5a1b-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="b5a1b-109">Développez l’arborescence, puis cliquez avec le bouton droit sur le pool dans lequel l’hôte autorisé a été créé.</span><span class="sxs-lookup"><span data-stu-id="b5a1b-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="b5a1b-110">Cliquez sur **Propriétés**, puis sur **Propriétés du front end**.</span><span class="sxs-lookup"><span data-stu-id="b5a1b-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="b5a1b-111">Cliquez sur l’onglet **autorisation d’hébergement** .</span><span class="sxs-lookup"><span data-stu-id="b5a1b-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="b5a1b-112">Sélectionnez un serveur, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b5a1b-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="b5a1b-113">Dans **Propriétés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5a1b-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

