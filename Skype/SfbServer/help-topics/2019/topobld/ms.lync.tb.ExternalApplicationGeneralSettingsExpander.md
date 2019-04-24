---
title: Développeur des paramètres généraux d’une application externe
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.
ms.openlocfilehash: 66f82f4e6dadf39cbfcce77c46cafc2fedd3d168
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220623"
---
# <a name="external-application-general-settings-expander"></a>Développeur des paramètres généraux d’une application externe
 
Pour modifier les propriétés d’un serveur d’applications approuvées qui a déjà été défini, suivez ces instructions.
  
Il existe deux sections que vous pouvez modifier :
  
> Paramètres généraux
> 
> Paramètres du tronçon suivant
    
## <a name="general-settings"></a>Paramètres généraux

Vous pouvez modifier le nom de domaine complet (FQDN) actuel pour le pool de serveurs d’applications approuvées. Modifiez le nom du pool de nom de domaine complet. Les enregistrements d’hôte (A) de nom de domaine DNS (Domain Name System) doivent exister pour que la nouvelle entrée avant de clients ou serveurs peuvent se connecter par le nouveau nom du pool.
  
Si vous avez besoin pour que la réplication des données de configuration pour ce pool, sélectionnez **Activer la réplication des données de configuration pour ce pool** . Désactivez la case à cocher si vous ne souhaitez pas répliquer les données de configuration.
  
## <a name="next-hop-settings"></a>Paramètres du tronçon suivant

Vous pouvez spécifier le serveur du tronçon suivant du pool serveur d’applications approuvées en sélectionnant le pool frontal Enterprise Edition ou Standard Edition serveur frontal dans la liste déroulante. Un directeur ou un directeur pool n’est pas une sélection valide pour une application approuvée tronçon suivant du serveur et n’apparaît pas dans la liste.
  

Cliquez sur **OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  

