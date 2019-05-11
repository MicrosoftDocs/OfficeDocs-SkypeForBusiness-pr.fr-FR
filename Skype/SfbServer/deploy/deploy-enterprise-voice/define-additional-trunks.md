---
title: Définition de jonctions supplémentaires dans le Générateur de topologie dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Résumé : Découvrez comment définir un tronçon supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologie dans Skype pour Business Server.'
ms.openlocfilehash: 308cd200af2ee046a3e2bcc84815d3755cea932f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892859"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Définition de jonctions supplémentaires dans le Générateur de topologie dans Skype pour Business Server
 
**Résumé :** Découvrez comment définir un tronçon supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologie dans Skype pour Business Server.
  
Suivez ces étapes pour définir un tronçon supplémentaire auquel vous pouvez associer un homologue à un serveur de médiation. Un homologue fournit aux utilisateurs activés pour Enterprise Voice avec une connectivité pour les publics téléphone réseau commuté (RTC). L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur ITSP (Internet Telephony Service Provider).
  
Une jonction est une connexion logique entre un serveur de médiation et une passerelle.
  
> [!NOTE]
> Cette rubrique suppose que vous disposez du programme d’installation une passerelle PSTN et jonction racine au moins un colocalisé ou autonome serveur de médiation ou pool comme décrit dans [définir une passerelle dans le Générateur de topologie dans Skype pour Business Server](define-a-gateway.md) dans la documentation de déploiement.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Pour définir un tronçon supplémentaire entre un serveur de médiation et un homologue de passerelle

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.
    
2. Sous Skype pour Business Server, le nom de votre site, **Composants partagés**, cliquez sur le nœud **tronçons** , puis cliquez sur **Nouvelle jonction**.
   1. Dans **Définir un nouveau tronçon**, spécifiez un nom convivial pour identifier le tronçon de manière unique. Deux tronçons ne peuvent pas porter le même nom.
    
      > [!NOTE]
      > Si vous spécifiez Transport Layer Security (TLS) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’homologue du serveur de médiation. 
  
3. Sous **Passerelle RTC associée**, sélectionnez l’homologue de passerelle RTC à associer à ce tronçon.
    5. Sous **Port d’écoute pour passerelle PSTN**, tapez le port d’écoute que l’homologue (passerelle PSTN, IP-PBX ou SBC) recevoir des messages SIP à partir du serveur de médiation doit être associé à ce tronçon. Les ports homologues par défaut sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security). Les ports de Survivable Branch Appliance par défaut sont 5081 pour TCP et 5082 pour TLS.
    
4. Dans **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.
    
    > [!NOTE]
    > Pour des raisons de sécurité, il est vivement recommandé de déployer un homologue pour le serveur de médiation pouvant utiliser TLS. 
  
5. Sous **Serveur de médiation associé**, sélectionnez le pool de serveur de médiation à associer à la jonction racine de cet homologue
    
6. Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation recevoir des messages SIP de l’homologue.
    
    > [!NOTE]
    > Plusieurs jonction prend en charge Skype pour Business Server, deux tronçons ayant des noms différents ne peuvent pas être configurés avec le même **port du serveur de médiation associé** et le **Port d’écoute pour passerelle IP/RTC**
  
    > [!NOTE]
    > Plusieurs jonction prend en charge Skype pour Business Server, SIP plusieurs voies de signalisation peut être définie sur le serveur de médiation pour la communication avec plusieurs homologues. Lors de la définition d’une jonction, le numéro de **port du serveur de médiation associé** doit se trouver dans la plage de ports d’écoute pour le protocole respectif autorisé par le serveur de médiation. Cette plage de ports est définie sous Skype pour les pools Business Server et le serveur de médiation. Le pool de serveur de médiation pertinent d’avec le bouton droit et sélectionnez **Modifier les propriétés**. Specify the port range in the **Listening ports** field.
  
7. Cliquez sur **OK**. 
    

