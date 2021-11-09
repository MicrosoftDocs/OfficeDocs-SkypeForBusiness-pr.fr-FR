---
title: Ajouter un pool MCU audio/vidéo
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Tous les serveurs frontaux Enterprise Edition d’un site central qui ne disposent pas d’un service de conférence A/V colocalisé peuvent utiliser le pool de conférence A/V autonome. Pour chaque pool de conférence A/V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et déterminer s’il aura un serveur de conférence A/V unique ou plusieurs serveurs de conférence A/V avec charge équilibrée.
ms.openlocfilehash: feb97e668ff2baf115b41295a5a798b856683ec2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839416"
---
# <a name="add-av-mcu-pool"></a>Ajouter un pool MCU audio/vidéo
 
Tous les serveurs frontaux Enterprise Edition d’un site central qui ne disposent pas d’un service de conférence A/V colocalisé peuvent utiliser le pool de conférence A/V autonome. Pour chaque pool de conférence A/V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et déterminer s’il aura un serveur de conférence A/V unique ou plusieurs serveurs de conférence A/V avec charge équilibrée.
  
> [!IMPORTANT]
> Vous ne pouvez pas convertir un pool d’un seul serveur en pool de plusieurs serveurs. Si vous décidez par la suite que votre organisation a besoin d’un pool de plusieurs serveurs, vous devez supprimer le pool d’un seul serveur, puis ajouter le pool de plusieurs serveurs. 
  
> [!TIP]
> Si vous envisagez d’implémenter un pool de conférence A/V par la suite, sélectionnez **Pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez à nouveau le Générateur de topologies pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool de conférence A/V via l’Assistant Déploiement de Skype Entreprise Server. Les pools du serveur de conférence A/V sont uniques, c’est-à-dire qu’ils ne requièrent pas de programmes d’équilibrage de charge pour créer un pool. Les pools de conférence A/V équilibrent la charge de manière interne et ne nécessitent pas de matériel supplémentaire. 
  

