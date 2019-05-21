---
title: Développeur des paramètres généraux d’une application externe
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez les instructions ci-dessous.
ms.openlocfilehash: 96118d968a5c9fdf54a78df24019426e562220dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292779"
---
# <a name="external-application-general-settings-expander"></a>Développeur des paramètres généraux d’une application externe
 
Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez les instructions ci-dessous.
  
Vous pouvez modifier deux sections:
  
> Paramètres généraux
> 
> Paramètres du tronçon suivant
    
## <a name="general-settings"></a>Paramètres généraux

Vous pouvez modifier l’actuel nom de domaine complet (FQDN) du pool de serveurs d’applications de confiance. Modifiez le nom du nom de domaine complet (FQDN) du pool. Les enregistrements d’hôte DNS (Domain Name System) doivent exister pour la nouvelle entrée avant qu’un client ou un serveur puisse se connecter au nouveau nom du pool.
  
Pour pouvoir répliquer les données de configuration vers ce pool, sélectionnez **activer la réplication des données de configuration** . Supprimez la coche si vous ne souhaitez pas répliquer les données de configuration.
  
## <a name="next-hop-settings"></a>Paramètres de saut suivant

Dans la liste déroulante, vous pouvez spécifier le serveur tronçon suivant du pool de serveurs d’applications de confiance en sélectionnant le serveur frontal Enterprise Edition défini dans la liste déroulante. Un réalisateur ou un pool de réalisateurs n’est pas une sélection valide pour le tronçon suivant d’un serveur d’applications de confiance et n’apparaîtra pas dans la liste.
  

Cliquez sur **OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  

