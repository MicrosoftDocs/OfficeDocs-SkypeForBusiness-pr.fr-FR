---
title: Définir une passerelle dans le Générateur de topologie dans Skype pour Business Server
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Résumé : Découvrez comment définir une passerelle PSTN dans le Générateur de topologie dans Skype pour Business Server.'
ms.openlocfilehash: 40658bf91513701cc41eb6efdb02e3976672f1f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892866"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Définir une passerelle dans le Générateur de topologie dans Skype pour Business Server
 
**Résumé :** Découvrez comment définir une passerelle PSTN dans le Générateur de topologie dans Skype pour Business Server.
  
Procédez comme suit pour utiliser le Générateur de topologie pour définir un homologue avec lequel vous pouvez associer un serveur de médiation pour fournir une connectivité au réseau téléphonique commuté (RTC) pour les utilisateurs activés pour Enterprise Voice. Un homologue pour le serveur de médiation peut être une passerelle PSTN, un IP-PBX ou un contrôleur de frontière Session (SBC) pour un Internet téléphonie Service fournisseur (ITSP) à laquelle vous vous connectez en configurant une jonction SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Pour définir un homologue pour le serveur de médiation

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.
    
2. Sous Skype pour Business Server, le nom de votre site, composants partagés, cliquez sur le nœud **Passerelles PSTN** , puis cliquez sur **Nouvelle passerelle PSTN**.
3. Dans **Définir une nouvelle passerelle IP/RTC**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.
    
    > [!NOTE]
    > Si vous spécifiez Transport Layer Security (TLS) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’homologue du serveur de médiation. 
  
4. Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle RTC, puis cliquez sur **Suivant**.

5. Définissez une jonction racine pour la passerelle RTC. Une jonction est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.
    
    {FQDN du serveur de médiation, port d’écoute de serveur de médiation (TLS ou TCP) : IP de la passerelle et le nom de domaine complet, port d’écoute de passerelle}
    
     - Lorsque vous définissez une passerelle PSTN dans le Générateur de topologie, vous devez définir une jonction racine pour ajouter correctement la passerelle PSTN à votre topologie.
    
     - Vous ne pouvez pas supprimer la jonction racine tant que la passerelle RTC associée n’est pas supprimée.
    
6. Sous **Port d’écoute pour passerelle IP/PSTN**, tapez le port d’écoute que la passerelle, PBX ou SBC utilisera pour les messages SIP à partir du serveur de médiation qui seront associés à la jonction racine de la passerelle PSTN. (Par défaut, les ports sont 5066 pour TCP [Transmission Control Protocol] et 5067 pour TLS [Transport Layer Security] sur une passerelle RTC, un autocommutateur privé [PBX] ou un contrôleur SBC. Sur un serveur Survivable Branch Appliance sur un site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)
    
7. Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Pour des raisons de sécurité, il est vivement recommandé de déployer un homologue pour le serveur de médiation pouvant utiliser TLS. 
  
8. Sous **Serveur de médiation associé**, sélectionnez le pool de serveur de médiation à associer à la jonction racine de cette passerelle PSTN.
    
9. Sous **port du serveur de médiation associé**, tapez le port d’écoute du serveur de médiation utilisera pour les messages SIP provenant de la passerelle.
    
    > [!NOTE]
    > Plusieurs jonction prend en charge Skype pour Business Server, vous pouvez définir plusieurs SIP signalisation ports sur le serveur de médiation pour la communication avec plusieurs passerelles PSTN. Lorsque vous définissez une jonction, le **port du serveur de médiation associé** doit être dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation. Cette plage de ports est définie sous Skype pour Business Server et les Pools de médiation. Cliquez sur le pool de serveur de médiation d’intérêt et sélectionnez **Modifier les propriétés**. Specify the port range in the **Listening ports** field.
  
10. N’oubliez pas que l’homologue que vous avez défini est en cours d’exécution et à l’aide du nom de domaine complet ou l’adresse IP que vous avez spécifié. Puis cliquez sur **Terminer**.
    
11. Cliquez sur le nœud **Skype pour Business Server** , puis cliquez sur **Publier la topologie**.
    

