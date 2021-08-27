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
ms.localizationpriority: medium
description: 'La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs de domaine XMPP en :'
ms.openlocfilehash: c442d0c4f5b5443e378be5afc031f7489860e42a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594304"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configuration des certificats et des stratégies d’accès de passerelle XMPP

La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs de domaine XMPP en :
  
- Messagerie instantanée et présence : personne à personne uniquement
    
- Création de contacts fédérés XMPP dans le client Skype Entreprise client
    
Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés XMPP, les stratégies s’appliquent aux utilisateurs de domaines fédérés XMPP, mais pas aux utilisateurs de fournisseurs de services de messagerie instantanée SIP (Session Initiation Protocol) ou aux domaines fédérés SIP. Vous configurez un partenaire fédéré XMPP pour chaque domaine fédéré XMPP avec qui vous souhaitez permettre à vos utilisateurs d’ajouter des contacts et de communiquer. Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP. 
  
> [!NOTE]
> La fonctionnalité XMPP est Skype Entreprise Server 2019, mais peut être poursuivie dans un serveur hérité en coexistence avec Skype Entreprise Server 2019. Assurez-vous que vous avez déjà déployé la passerelle XMPP du serveur hérité (Skype Entreprise Server 2015 / Lync Server 2013) et configuré les stratégies d’accès pour permettre aux utilisateurs d’accéder à la passerelle XMPP héritée. Pour plus d’informations, [voir Migration de la fédération XMPP.](migrating-xmpp-federation.md) 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurer une stratégie d’accès externe pour activer les utilisateurs pour la passerelle XMPP héritée

1. Ouvrez le panneau de Skype Entreprise Server hérité.
    
2. Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Stratégie d’accès externe**.
    
3. Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.
    
4. Entrez un nom pour la stratégie utilisateur d’accès externe.
    
5. Fournissez une description pour la stratégie utilisateur d’accès externe.
    
6. Sélectionnez **Activer les communications avec les utilisateurs fédérés**.
    
7. Sélectionnez **Activer les communications avec les utilisateurs fédérés XMPP**.
    
8. Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie de site ou utilisateur. 
    

