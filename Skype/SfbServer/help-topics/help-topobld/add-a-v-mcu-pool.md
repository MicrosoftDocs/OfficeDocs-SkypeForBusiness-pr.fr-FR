---
title: Ajouter un pool MCU audio/vidéo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Les serveurs frontaux Enterprise Edition d’un site central ne disposant pas d’un service de conférence A/V colocalisé peuvent utiliser le même pool de conférence A/V autonome. Pour chaque pool de conférence A/V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et savoir s’il n’en a qu’un seul ou plusieurs serveurs de conférence A/V.
ms.openlocfilehash: 1d78a9d24659ec2ad571c01528323796e7ae5d18
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821316"
---
# <a name="add-av-mcu-pool"></a>Ajouter un pool MCU audio/vidéo
 
Les serveurs frontaux Enterprise Edition d’un site central ne disposant pas d’un service de conférence A/V colocalisé peuvent utiliser le même pool de conférence A/V autonome. Pour chaque pool de conférence A/V, vous devez spécifier un nom de domaine complet (FQDN) pour le pool et savoir s’il n’en a qu’un seul ou plusieurs serveurs de conférence A/V.
  
> [!IMPORTANT]
> Vous ne pouvez pas convertir un pool serveur unique en pool de plusieurs serveurs. Si vous décidez plus tard que votre organisation a besoin d’un pool de serveurs multiples, vous devez supprimer le pool de serveur unique, puis ajouter le pool de serveurs multiples. 
  
> [!TIP]
> Si vous envisagez d’implémenter un pool de conférence A/V à l’avenir, sélectionnez **plusieurs pools d’ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter plus d’ordinateurs au pool par la suite, vous devez de nouveau définir le générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du groupe de conférence A/V par le biais de l’Assistant Déploiement de Skype entreprise Server. Les pools de serveurs de conférence A/V sont uniques dans le fait qu’ils n’ont pas besoin des équilibreurs de charge pour créer un pool. Les pools de conférence A/V sont équilibrés en interne et ne nécessitent pas de matériel supplémentaire. 
  

