---
title: Agrandissement des paramètres généraux de l’Application externe
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez ces instructions.
ms.openlocfilehash: 4104b9cf22a3db36afd159c0b7d9812142112ece
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="external-application-general-settings-expander"></a>Agrandissement des paramètres généraux de l’Application externe
 
Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez ces instructions.
  
Il existe deux sections que vous pouvez modifier :
  
> Paramètres généraux
    
> Paramètres du tronçon suivant
    
## <a name="general-settings"></a>Paramètres généraux

Vous pouvez modifier le nom de domaine complet (FQDN) en cours pour le pool de serveur d’application de confiance. Modifier le nom de la grappe de nom de domaine complet. Les enregistrements de l’hôte (A) du système de nom de domaine (DNS) doivent exister pour la nouvelle entrée avant de clients ou de serveurs peuvent se connecter par le nouveau nom du pool.
  
Si vous avez besoin pour que la réplication des données de configuration pour ce pool, sélectionnez **Activer la réplication des données de configuration pour ce pool** . Désactivez la case à cocher si vous ne souhaitez pas répliquer les données de configuration.
  
## <a name="next-hop-settings"></a>Les paramètres de saut suivant

Vous pouvez spécifier le serveur du tronçon suivant la confiance server pool d’applications en sélectionnant le pool frontal de Enterprise Edition ou Standard Edition serveur frontal dans la liste déroulante. Un directeur ou un directeur pool n’est pas une sélection valide pour un saut suivant du serveur application sécurisée et n’apparaîtra pas dans la liste.
  
## 

Cliquez sur **OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  

