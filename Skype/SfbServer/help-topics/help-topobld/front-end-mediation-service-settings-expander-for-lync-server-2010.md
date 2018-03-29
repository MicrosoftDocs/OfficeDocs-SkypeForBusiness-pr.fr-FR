---
title: Expander de paramètres de Service de médiation Front-End pour Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Vous modifiez les propriétés des paramètres dans cette boîte de dialogue passerelle RTPC de serveur de médiation. Vous définissez les paramètres suivants :'
ms.openlocfilehash: e3ec392aac08121296769a9d5170886c61c7511b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expander de paramètres de Service de médiation Front-End pour Lync Server 2010
 
Vous modifiez les propriétés des paramètres dans cette boîte de dialogue **passerelle PSTN de serveur de médiation** . Vous définissez les paramètres suivants :
  
- Sélectionnez **serveur de médiation colocalisés activé** si vous souhaitez que le serveur de médiation avec ce serveur frontal ou Front-End des pools de colocaliser.
    
- **Ports d’écoute**: définir les ports qui écoute sur le serveur de médiation. Vous pouvez définir un port pour la sécurité de la couche transport ou **TLS** ou **TCP**, ou le protocole de contrôle de transport. Pour l’entrée de port pour TCP soit disponible, vous devez sélectionner la case à cocher pour **Activer le TCP port**. 
    
    > [!IMPORTANT]
    > Reportez-vous à la documentation et configuration pour votre passerelle de réseau téléphonique public commuté pour déterminer si vous devez activer et définir les valeurs de port TLS, TCP ou les deux. TLS est un protocole plus sécurisé, l’utilisation de certificats pour crypter le trafic entre le serveur de médiation et la passerelle RTC. Les passerelles RTPC pas tous en charge TLS. 
  
- Une liste répertorie les **jonctions** (jonctions SIP [Session Initiation Protocol]), la **passerelle** (passerelle RTC ou système IP-PBX) et le **site** (site configuré pour la jonction et la passerelle).
    
- Sélectionnez une jonction, une passerelle et un site et cliquez sur **Utiliser par défaut** pour définir la sélection comme valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler par défaut** pour supprimer la sélection comme valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut et cliquez sur **Utiliser par défaut**.
    
 **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
 **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
 **Aide** : permet d’afficher cet écran d’aide.
  

