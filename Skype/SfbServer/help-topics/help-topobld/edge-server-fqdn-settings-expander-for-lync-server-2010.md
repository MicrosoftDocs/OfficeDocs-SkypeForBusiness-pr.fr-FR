---
title: Edge Server FQDN paramètres Expander pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Pour définir les propriétés de paramètres externe, vous devez configurer les éléments suivants :'
ms.openlocfilehash: 2954c9add818e67f471cfb97893fef42e862bea3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="7b58a-103">Edge Server FQDN paramètres Expander pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7b58a-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="7b58a-104">Pour définir les propriétés de **paramètres externe**, vous devez configurer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7b58a-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="7b58a-105">Sélectionnez le **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** case à cocher si vous souhaitez définir différents FQDN du Pool et IP adresses pour la conférence web et audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="7b58a-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b58a-106">Si vous choisissez pour ne pas sélectionner la case à cocher pour les adresses IP et de nom de domaine complet séparés, vous devez fournir des ports distincts pour chacun des trois services fournis par le serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="7b58a-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="7b58a-107">Le seul nom de domaine pleinement qualifié qui consiste à configurer est le nom de domaine complet associé au service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="7b58a-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="7b58a-108">Sélectionnez le **A / V Edge service NAT activé** case à cocher si vous souhaitez que le A / service V Edge d’utiliser un réseau adresse adresse IP de la traduction (NAT) et la configuration.</span><span class="sxs-lookup"><span data-stu-id="7b58a-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="7b58a-109">Pour les services de bord activés, vous tapez un **Nom de domaine complet Pool** et un port sous **Ports**</span><span class="sxs-lookup"><span data-stu-id="7b58a-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="7b58a-110">Définir le nom de domaine complet Pool **service Edge d’accès** et d’un port qui identifie le service.</span><span class="sxs-lookup"><span data-stu-id="7b58a-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="7b58a-111">Définir le nom de domaine complet de **serveur Edge de conférence Web service** Pool (si activer de séparer le nom de domaine complet et l’adresse IP pour les conférences web et A / V n’est pas sélectionnée) et un port qui identifie le service.</span><span class="sxs-lookup"><span data-stu-id="7b58a-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="7b58a-112">Définir la **A / V Edge service** FQDN du Pool (si activer de séparer le nom de domaine complet et l’adresse IP pour les conférences web et A / V n’est pas sélectionnée) et un port qui identifie le service.</span><span class="sxs-lookup"><span data-stu-id="7b58a-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
 <span data-ttu-id="7b58a-113">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="7b58a-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="7b58a-114">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="7b58a-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="7b58a-115">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="7b58a-115">**Help** Displays this help screen.</span></span>
  

