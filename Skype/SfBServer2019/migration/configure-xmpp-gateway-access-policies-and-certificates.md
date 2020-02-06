---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La Fédération XMPP définit un déploiement externe en fonction du protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs de domaine XMPP en procédant comme suit :'
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813762"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configuration des certificats et des stratégies d’accès de passerelle XMPP

La Fédération XMPP définit un déploiement externe en fonction du protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs de domaine XMPP en procédant comme suit :
  
- Messagerie instantanée et présence-personne uniquement
    
- Création de contacts fédérés de XMPP dans le client Skype entreprise
    
Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés XMPP, les stratégies s’appliquent aux utilisateurs des domaines fédérés de XMPP, mais pas aux utilisateurs des fournisseurs de services de messagerie instantanée SIP (Session Initiation Protocol) ou de domaines fédérés SIP. Vous configurez un partenaire fédéré de XMPP pour chaque domaine fédéré XMPP que vous voulez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec eux. Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP. 
  
> [!NOTE]
> La fonctionnalité XMPP est déconseillée dans Skype entreprise Server 2019, mais peut être poursuivie dans un serveur hérité pour coexistence avec Skype entreprise Server 2019. Assurez-vous d’avoir déjà déployé le serveur hérité (Skype entreprise Server 2015/Lync Server 2013) et configuré les stratégies d’accès pour permettre aux utilisateurs de la passerelle XMPP héritée. Pour plus d’informations, consultez Migration de la [Fédération XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurer une stratégie d’accès externe pour permettre aux utilisateurs de l’ancienne passerelle XMPP

1. Ouvrez l’ancien panneau de configuration Skype entreprise Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **stratégie d’accès externe**.
    
3. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
4. Entrez le nom de la stratégie de l’utilisateur pour l’accès externe.
    
5. Entrez une description pour la stratégie utilisateur d’accès externe.
    
6. Sélectionnez **activer les communications avec les utilisateurs fédérés**.
    
7. Sélectionnez **activer les communications avec les utilisateurs fédérés de XMPP**.
    
8. Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie de site ou d’utilisateur. 
    

