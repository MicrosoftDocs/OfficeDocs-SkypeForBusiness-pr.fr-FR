---
title: Définir des branches supplémentaires dans le Générateur de topologies dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Résumé : Découvrez comment définir une branche supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologies dans Skype Entreprise Server.'
ms.openlocfilehash: a3a1094bdc9d0f92eba5cfa1ace87f14db0011de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748870"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Définir des branches supplémentaires dans le Générateur de topologies dans Skype Entreprise Server
 
**Résumé :** Découvrez comment définir une branche supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologies dans Skype Entreprise Server.
  
Suivez ces étapes pour définir une ligne supplémentaire à laquelle vous pouvez associer un homologue à un serveur de médiation. Un homologue fournit aux utilisateurs activés Voix Entreprise la connectivité au réseau téléphonique commuté (PSTN). Un homologue peut être une passerelle PSTN, un SYSTÈME IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP).
  
Une connexion est une connexion logique entre un serveur de médiation et une passerelle.
  
> [!NOTE]
> Cette rubrique suppose que vous avez configuré une passerelle PSTN et une troncation racine avec au moins un serveur ou pool de médiation c c colloc ou autonome, comme décrit dans Définir une passerelle dans le Générateur de topologies dans [Skype Entreprise Server](define-a-gateway.md) dans la documentation de déploiement.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Pour définir une ligne supplémentaire entre un serveur de médiation et un homologue de passerelle

1. Démarrez le Générateur de topologie : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server 2015,** puis sur Skype Entreprise Server **2015Topology Builder**.
    
2. Sous Skype Entreprise Server, nom de votre site, **Composants partagés,** cliquez avec le bouton droit sur le nœud **Trunks,** puis cliquez sur **New Trunk**.
   1. Dans **Définir une nouvelle trunk**, spécifiez un nom convivial pour identifier la trunk de manière unique. Vous ne pouvez pas avoir deux branches du même nom.
    
      > [!NOTE]
      > Si vous spécifiez le type de transport TLS (Transport Layer Security), vous devez spécifier le nom de groupe au lieu de l’adresse IP de l’homologue du serveur de médiation. 
  
3. Sous **Passerelle PSTN associée,** sélectionnez l’homologue de passerelle PSTN à associer à cette passerelle.
    5. Sous Le port d’écoute pour la passerelle **PSTN,** tapez le port d’écoute que l’homologue (passerelle PSTN, IP-PBX ou SBC) recevra des messages SIP du serveur de médiation qui doit être associé à cette passerelle. Les ports homologues par défaut sont 5066 pour le protocole TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security). Les ports survivable Branch Appliance par défaut sont 5081 pour TCP et 5082 pour TLS.
    
4. Sous **Protocole de transport SIP,** cliquez sur le type de transport utilisé par l’homologue.
    
    > [!NOTE]
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser TLS. 
  
5. Sous **Serveur de médiation associé,** sélectionnez le pool de serveurs de médiation à associer à la branche racine de cet homologue
    
6. Sous **le port du serveur de médiation associé,** tapez le port d’écoute que le serveur de médiation recevra des messages SIP de l’homologue.
    
    > [!NOTE]
    > Avec la prise en charge de plusieurs trunks dans Skype Entreprise Server, deux trunks avec des noms de trunks différents ne peuvent pas être configurés avec le même port de serveur de médiation associé et le même **port** d’écoute pour la passerelle **IP/PSTN**
  
    > [!NOTE]
    > Avec la prise en charge de plusieurs Skype Entreprise Server, plusieurs ports de signalisation SIP peuvent être définis sur le serveur de médiation pour la communication avec plusieurs homologues. Lors de la définition d’une trunk, le numéro de **port** du serveur de médiation associé doit se trouver dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation. Cette plage de ports est définie sous Skype Entreprise Server pools de serveurs de médiation et de médiation. Cliquez avec le bouton droit sur le pool de serveurs de médiation approprié, puis **sélectionnez Modifier les propriétés.** Spécifiez la plage de ports dans le champ **Ports d’écoute**.
  
7. Cliquez sur **OK**. 
    

