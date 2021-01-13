---
title: Expanseur des paramètres généraux d’une application externe
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.
ms.openlocfilehash: 8cdf27598c916f84e96b11d8acfaeb115a0575dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822424"
---
# <a name="external-application-general-settings-expander"></a>Expandeur des paramètres généraux d’une application externe
 
Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.
  
Deux sections peuvent être modifiées :
  
> Paramètres généraux
> 
> Paramètres du tronçon suivant
    
## <a name="general-settings"></a>Paramètres généraux

Vous pouvez modifier le nom de domaine complet actuel du pool de serveurs d’applications approuvées. Modifiez le nom de domaine complet du pool. Les enregistrements d’hôte DNS (Domain Name System) (A) doivent exister pour la nouvelle entrée pour que les clients ou les serveurs puissent se connecter au nouveau nom de pool.
  
Sélectionnez **Activer la réplication des données de configuration sur ce pool** si les données de configuration doivent être répliquées sur ce pool. Désactivez la case à cocher si vous ne voulez pas répliquer les données de configuration.
  
## <a name="next-hop-settings"></a>Paramètres du tronçon suivant

Vous pouvez spécifier le serveur du saut suivant du pool de serveurs d’applications approuvé en sélectionnant le pool frontal Enterprise Edition défini ou le serveur frontal Standard Edition dans la liste liste. Un directeur ou un pool de directeurs n’est pas un choix valide pour un tronçon suivant de serveur d’applications approuvées et n’apparaîtra pas dans la liste.
  

Cliquez **sur OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  

