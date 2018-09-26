---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La fédération XMPP définit un déploiement externe en fonction des eXtensible Messaging et présence protocole XMPP (). Une configuration XMPP permet aux utilisateurs d’accéder à des utilisateurs de domaine XMPP par :'
ms.openlocfilehash: 2ec2440365907632523728238c51cc90e894c84e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027857"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configuration des certificats et des stratégies d’accès de passerelle XMPP

La fédération XMPP définit un déploiement externe en fonction des eXtensible Messaging et présence protocole XMPP (). Une configuration XMPP permet aux utilisateurs d’accéder à des utilisateurs de domaine XMPP par :
  
- Messagerie instantanée et présence - personne à personne uniquement
    
- Création de contacts fédérés XMPP dans le Skype pour client d’entreprise
    
Lorsque vous configurez les stratégies de prise en charge de XMPP les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines XMPP fédéré, mais pas aux utilisateurs de protocole d’ouverture de session (SIP) (IM) service de messagerie instantanée fournisseurs ou SIP des domaines fédérés. Vous configurez un partenaire fédéré XMPP pour chaque domaine fédéré XMPP que vous souhaitez autoriser les utilisateurs à ajouter des contacts et communiquez avec. Une fois que les stratégies sont en place, vous devez configurer les certificats de passerelle XMPP. 
  
> [!NOTE]
> La fonctionnalité XMPP est déconseillée dans Skype pour Business Server 2019, mais peut être poursuivie dans un serveur hérité en coexistence avec Skype pour Business Server 2019. Assurez-vous que vous avez déjà déployé le serveur hérité (Skype pour Business Server 2015 / Lync Server 2013), la passerelle XMPP et configuré les stratégies d’accès pour permettre aux utilisateurs pour la passerelle XMPP hérité. Pour plus d’informations, consultez la rubrique [Migrer la fédération XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurer une stratégie d’accès externe pour activer des utilisateurs pour la passerelle XMPP hérité

1. Ouvrez le Skype hérité pour le panneau de configuration serveur Business.
    
2. Dans la barre de navigation de gauche, cliquez sur **fédération et accès externe**, puis cliquez sur **Stratégie d’accès externe**.
    
3. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
4. Entrez un nom pour la stratégie utilisateur d’accès externe.
    
5. Fournissez une description pour la stratégie utilisateur d’accès externe.
    
6. Sélectionnez **Activer les communications avec les utilisateurs fédérés**.
    
7. Sélectionnez **Autoriser les communications avec XMPP des utilisateurs fédérés**.
    
8. Cliquez sur **Valider** pour enregistrer vos modifications à la stratégie de site ou utilisateur. 
    

