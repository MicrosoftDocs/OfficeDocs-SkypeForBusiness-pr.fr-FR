---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs du domaine XMPP en :'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753934"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configuration des certificats et des stratégies d’accès de passerelle XMPP

La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs du domaine XMPP en :
  
- Messagerie instantanée et présence-personne à personne uniquement
    
- Création de contacts fédérés XMPP dans le client Skype entreprise
    
Lorsque vous configurez des stratégies de prise en charge des partenaires fédérés XMPP, les stratégies s’appliquent aux utilisateurs de domaines fédérés XMPP, mais pas aux utilisateurs de fournisseurs de services de messagerie instantanée SIP (Session Initiation Protocol) ou de domaines fédérés SIP. Vous configurez un partenaire fédéré XMPP pour chaque domaine fédéré XMPP pour lequel vous souhaitez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec. Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP. 
  
> [!NOTE]
> La fonctionnalité XMPP est déconseillée dans Skype entreprise Server 2019, mais peut être poursuivie dans un serveur hérité en coexistence avec Skype entreprise Server 2019. Assurez-vous que vous avez déjà déployé le serveur hérité (Skype entreprise 2015 Server 2013), passerelle XMPP, et configuré les stratégies d’accès pour activer les utilisateurs pour la passerelle XMPP héritée. Pour plus d’informations, consultez la rubrique migration de la [Fédération XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurer une stratégie d’accès externe pour activer les utilisateurs pour la passerelle XMPP héritée

1. Ouvrez le panneau de configuration hérité de Skype entreprise Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Stratégie d’accès externe**.
    
3. Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.
    
4. Entrez un nom pour la stratégie utilisateur d’accès externe.
    
5. Fournissez une description pour la stratégie utilisateur d’accès externe.
    
6. Sélectionnez **Activer les communications avec les utilisateurs fédérés**.
    
7. Sélectionnez **Activer les communications avec les utilisateurs fédérés XMPP**.
    
8. Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie de site ou utilisateur. 
    

