---
title: Ajouter A / V MCU Pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Tous les serveurs Enterprise Edition avant fin d’un site central qui n’ont pas un colocalisé A V Conferencing service peut utiliser la même A autonome / pool de V Conferencing. Pour chaque A / pool de V Conferencing, vous devez spécifier un nom de domaine pleinement qualifié (FQDN) pour le pool et si elle a seulement seul un / V Conferencing Server ou multiples, avec équilibrage de charge A / V Conferencing serveurs.
ms.openlocfilehash: d1712829030836446c06a2e335c424d51a19e466
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-av-mcu-pool"></a>Ajouter A / V MCU Pool
 
Tous les serveurs Enterprise Edition avant fin d’un site central qui n’ont pas un colocalisé A V Conferencing service peut utiliser la même A autonome / pool de V Conferencing. Pour chaque A / pool de V Conferencing, vous devez spécifier un nom de domaine pleinement qualifié (FQDN) pour le pool et si elle a seulement seul un / V Conferencing Server ou multiples, avec équilibrage de charge A / V Conferencing serveurs.
  
> [!IMPORTANT]
> Vous ne pouvez pas convertir un pool de serveur unique vers un regroupement de plusieurs serveurs. Si vous décidez ultérieurement que votre organisation a besoin d’un pool de plusieurs serveurs, vous devez supprimer le pool de serveur unique et ensuite ajouter le pool de plusieurs serveurs. 
  
> [!TIP]
> Si vous envisagez d’implémenter un A / pool de V Conferencing sélectionnez à l’avenir, **plusieurs pool d’ordinateur**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec équilibrage de la charge, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez le Générateur de topologies pour définir le nouveau membre du pool, publiez la nouvelle topologie, puis configurer le nouveau A / V Conferencing pool membre via le Skype pour l’Assistant de déploiement de Business Server. A / pools de V Conferencing Server sont uniques car ils ne pas besoin équilibreurs de charge pour créer un pool. A / pools de V Conferencing équilibrer la charge en interne et n’avez pas besoin de matériel supplémentaire. 
  

