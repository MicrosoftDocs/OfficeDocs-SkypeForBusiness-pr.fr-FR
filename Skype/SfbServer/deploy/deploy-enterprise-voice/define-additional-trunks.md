---
title: Définition de lignes supplémentaires dans le générateur de topologies de Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Résumé : Découvrez comment définir un Trunk supplémentaire entre un serveur de médiation et un homologue de passerelle dans le générateur de topologies de Skype entreprise Server.'
ms.openlocfilehash: afd8a37272d7450115f688bafe3627fb2689903c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767717"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Définition de lignes supplémentaires dans le générateur de topologies de Skype entreprise Server
 
**Résumé :** Découvrez comment définir un Trunk supplémentaire entre un serveur de médiation et un homologue de passerelle dans le générateur de topologies de Skype entreprise Server.
  
Procédez comme suit pour définir un Trunk supplémentaire auquel vous pouvez associer un homologue à un serveur de médiation. Un homologue fournit aux utilisateurs une connectivité voix entreprise compatible avec le réseau téléphonique commuté (PSTN). L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur ITSP (Internet Telephony Service Provider).
  
Un Trunk est une connexion logique entre un serveur de médiation et une passerelle.
  
> [!NOTE]
> Dans cette rubrique, nous partons du principe que vous avez configuré une passerelle RTC et une Trunk racine avec au moins un serveur ou un pool de médiation autonome ou autonome comme décrit dans la rubrique [définir une passerelle dans le générateur de topologie de Skype entreprise Server](define-a-gateway.md) dans la documentation de déploiement.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Pour définir un Trunk supplémentaire entre un serveur de médiation et un homologue de passerelle

1. Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.
    
2. Sous Skype entreprise Server, le nom de votre site, les **composants partagés**, cliquez avec le bouton droit sur le nœud **Trunks** , puis cliquez sur **nouveau Trunk**.
   1. Dans **Définir un nouveau tronçon**, spécifiez un nom convivial pour identifier le tronçon de manière unique. Deux tronçons ne peuvent pas porter le même nom.
    
      > [!NOTE]
      > Si vous spécifiez TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet (FQDN) au lieu de l’adresse IP de l’homologue du serveur de médiation. 
  
3. Sous **Passerelle RTC associée**, sélectionnez l’homologue de passerelle RTC à associer à ce tronçon.
    5. Sous **port d’écoute pour la passerelle RTC**, tapez le port d’écoute que le pair (passerelle PSTN, IP-PBX ou SBC) reçoit les messages SIP du serveur de médiation qui sera associé à ce Trunk. Les ports homologues par défaut sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security). Les ports de l’appareil de branchement Survivable par défaut sont 5081 pour TCP et 5082 pour TLS.
    
4. Dans **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.
    
    > [!NOTE]
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser le protocole TLS. 
  
5. Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer au Trunk racine de cet homologue.
    
6. Sous **port du serveur de médiation associé**, tapez le port d’écoute sur lequel le serveur de médiation va recevoir des messages SIP de l’homologue.
    
    > [!NOTE]
    > Grâce à la prise en charge de Trunks multiples dans Skype entreprise Server, il est impossible de configurer deux Trunks avec différents noms de Trunk avec les mêmes **port de serveur de médiation** et **port d’écoute pour une passerelle IP/RTC**
  
    > [!NOTE]
    > La prise en charge de plusieurs Trunks dans Skype entreprise Server vous permet de définir plusieurs ports de signalisation SIP sur le serveur de médiation pour la communication avec des pairs multiples. Lors de la définition d’un Trunk, le numéro de **port du serveur de médiation associé** doit figurer dans la plage des ports d’écoute pour le protocole correspondant autorisé par le serveur de médiation. Cette plage de ports est définie sous Skype entreprise Server et pools de serveurs de médiation. Cliquez avec le bouton droit sur la liste de serveurs de médiation appropriée, puis sélectionnez **modifier les propriétés**. Specify the port range in the **Listening ports** field.
  
7. Cliquez sur **OK**. 
    

