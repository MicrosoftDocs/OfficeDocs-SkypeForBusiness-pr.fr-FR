---
title: Expanseur des paramètres du Service de Front-End médiation pour Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Vous modifiez les propriétés des paramètres de la passerelle PSTN de serveur de médiation dans cette boîte de dialogue. Vous définissez les paramètres suivants :'
ms.openlocfilehash: fa3038e8480fb11430388c95914750ab1d9ca68c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971987"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expanseur des paramètres du Service de Front-End médiation pour Lync Server 2010
 
Vous modifiez les propriétés des paramètres de la **passerelle PSTN de serveur de médiation** dans cette boîte de dialogue. Vous définissez les paramètres suivants :
  
- Sélectionnez **serveur de médiation colocalisé activé** si vous voulez colocaliser le serveur de médiation avec ce serveur frontal ou pools frontaux.
    
- **Ports d’écoute**: définir les ports d’écoute sur le serveur de médiation. Vous pouvez définir un port pour **TLS** ou transport layer security, ou **TCP**, ou le protocole de transport. Pour l’entrée de port TCP soit disponible, vous devez sélectionner la case à cocher pour **le port TCP activer**. 
    
    > [!IMPORTANT]
    > Consultez les paramètres de configuration et de la documentation de votre passerelle de réseau téléphonique commuté pour déterminer si vous souhaitez activer et définir les valeurs de ports TLS, TCP ou les deux. TLS est un protocole plus sécurisé, l’utilisation de certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN. Pas toutes les passerelles PSTN prend en charge TLS. 
  
- Une liste répertorie les **jonctions** (jonctions SIP [Session Initiation Protocol]), la **passerelle** (passerelle RTC ou système IP-PBX) et le **site** (site configuré pour la jonction et la passerelle).
    
- Sélectionnez une jonction, une passerelle et un site et cliquez sur **Utiliser par défaut** pour définir la sélection comme valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler par défaut** pour supprimer la sélection comme valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut et cliquez sur **Utiliser par défaut**.
    
 **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
 **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
 **Aide** : permet d’afficher cet écran d’aide.
  

