---
title: Modification des URL simples après la migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype pour Business Server prend en charge les URL simples.
ms.openlocfilehash: 02f4cc729a50459a8125e216265b935d557007c6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238750"
---
# <a name="change-simple-urls-after-migration"></a>Modification des URL simples après la migration

Skype pour Business Server prend en charge trois URL simples :
  
- **Répondre à** est utilisée comme URL de base pour toutes les conférences dans le site ou une organisation. Avec l’URL simple Meet, liens à participer à des réunions sont faciles à comprendre et à communiquer et à distribuer. 
    
- **Rendez-vous** permettant d’accéder à la page Web paramètres de conférence rendez-vous. L’URL simple Dial-in est inclus dans toutes les invitations aux réunions afin que les utilisateurs qui souhaitent se connecter à la réunion peuvent accéder au numéro de téléphone nécessaire et les informations de code confidentiel. 
    
- **Admin** permet d’accéder rapidement à la Skype pour le panneau de configuration serveur Business. L’URL simple Admin est interne à votre organisation. 
    
Après avoir migré vers Skype pour Business Server, vous devez être conscient de la modification de l’impact de vos enregistrements DNS et les certificats pour les URL simples. Si le Skype hérité pour le directeur Business Server continue à être utilisé dans la topologie, aucune modification des URL simples n’est requise. Si le Skype pour le directeur Business Server est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour pour pointer vers un de la Skype pour les pools de serveurs d’entreprise. Toutefois, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque directeur et le serveur frontal pour enregistrer la modification.

## <a name="to-update-the-meet-simple-url"></a>Pour mettre à jour l’URL simple Meet

1. Dans le Générateur de topologie, cliquez sur le nœud supérieur **Skype pour Business Server**, puis cliquez sur **Modifier les propriétés**.
    
2. Sélectionnez les **URL simples** dans le volet gauche, puis sous **URL de réunion :** sélectionnez l’URL Meet, puis cliquez sur **Modifier l’URL**.
    
3. Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée. 
    
## <a name="to-update-the-admin-simple-url"></a>Pour mettre à jour l’URL simple Admin

1. Dans le Générateur de topologie, cliquez sur le nœud supérieur **Skype pour Business Server**, puis cliquez sur **Modifier les propriétés**.
    
2. Sélectionnez **URL simples** dans le volet gauche, puis sous la zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour un accès administratif à Skype pour Business Server le panneau de configuration, puis cliquez sur **OK**.
    
   > [!TIP]
   > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration. L’option la plus simple est https://admin. <em> \<domaine\></em>. 
  
## <a name="see-also"></a>Voir aussi

[Enregistrements DNS requis pour les URL simples dans Skype pour Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
