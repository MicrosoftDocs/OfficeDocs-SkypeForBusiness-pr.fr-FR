---
title: "Expanseur des paramètres du service de médiation frontal pour Lync Server\_2010"
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: "Vous modifiez les propriétés des paramètres de Passerelle PSTN du serveur de médiation dans cette boîte de dialogue. Vous définissez les paramètres suivants\_:"
---

# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expandeur des paramètres du service de médiation frontal pour Lync Server 2010
 
Vous modifiez les propriétés des paramètres de **Passerelle PSTN du serveur de médiation** dans cette boîte de dialogue. Vous définissez les paramètres suivants :
  
- Sélectionnez **le serveur** de médiation cocéré activé si vous souhaitez c céquerifier le serveur de médiation avec ce serveur frontal ou ce pools frontux.
    
- **Ports d’écoute** : définissez les ports que le serveur de médiation écoutera. Vous pouvez définir un port pour le protocole **TLS** (Transport Layer Security) ou **TCP** (Transport Control Protocol). Pour que l’entrée du port TCP soit disponible, vous devez activer la case à cocher **Activer le port TCP**. 
    
    > [!IMPORTANT]
    > Consultez la documentation et les paramètres de configuration de votre passerelle de réseau téléphonique commuté (PSTN) pour déterminer si vous devez activer et définir les valeurs du port TLS, TCP ou les deux. TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN. Certaines passerelles PSTN ne prennent pas en charge TLS. 
  
- Une liste d’éléments existants et actuellement associés en matière de **Jonction** (c’est-à-dire, jonctions SIP (Session Initiation Protocol)), de **Passerelle** (passerelle PSTN ou système IP-PBX) et de **Site** (site configuré pour la jonction et la passerelle).
    
- Sélectionnez une jonction, une passerelle et un site, puis cliquez sur **Utiliser par défaut** pour définir la sélection en tant que valeur par défaut pour ce service de médiation. Sélectionnez la valeur par défaut actuelle, puis cliquez sur **Annuler Par défaut** pour supprimer la sélection en tant que valeur par défaut actuelle. Sélectionnez ensuite une nouvelle valeur par défaut, puis cliquez sur **Utiliser par défaut**.
    
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  

