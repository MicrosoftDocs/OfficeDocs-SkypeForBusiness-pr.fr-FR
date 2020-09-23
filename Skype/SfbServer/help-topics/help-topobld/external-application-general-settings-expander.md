---
title: Expanseur des paramètres généraux d’une application externe
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218135"
---
# <a name="external-application-general-settings-expander"></a>Expanseur des paramètres généraux d’une application externe
 
Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.
  
Deux sections peuvent être modifiées :
  
> Paramètres généraux
> 
> Paramètres du tronçon suivant
    
## <a name="general-settings"></a>Paramètres généraux

Vous pouvez modifier le nom de domaine complet actuel du pool de serveurs d’applications approuvées. Modifiez le nom de domaine complet du pool. Les enregistrements d’hôte DNS (Domain Name System) (A) doivent exister pour la nouvelle entrée pour que les clients ou les serveurs puissent se connecter au nouveau nom de pool.
  
Sélectionnez **Activer la réplication des données de configuration sur ce pool** si les données de configuration doivent être répliquées sur ce pool. Désactivez la case à cocher si vous ne voulez pas répliquer les données de configuration.
  
## <a name="next-hop-settings"></a>Paramètres du tronçon suivant

Vous pouvez spécifier le serveur du tronçon suivant du pool de serveurs d’applications approuvées en sélectionnant le pool frontal Enterprise Edition défini ou le serveur frontal Standard Edition dans la liste déroulante. Un directeur ou un pool de directeurs n’est pas un choix valide pour un tronçon suivant de serveur d’applications approuvées et n’apparaîtra pas dans la liste.
  


Cliquez sur **OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  

