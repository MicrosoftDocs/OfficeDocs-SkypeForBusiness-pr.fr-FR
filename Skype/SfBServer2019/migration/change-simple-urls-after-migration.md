---
title: Modification des URL simples après la migration
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
description: Skype entreprise Server prend en charge les URL simples.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753904"
---
# <a name="change-simple-urls-after-migration"></a>Modification des URL simples après la migration

Skype entreprise Server prend en charge trois URL simples :
  
- **Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute. 
    
- **Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information. 
    
- L' **administrateur** vous permet d’accéder rapidement au panneau de configuration de Skype entreprise Server. L’URL simple d’administration est interne à votre organisation. 
    
Après avoir effectué la migration vers Skype entreprise Server, vous devez savoir comment la modification influe sur vos enregistrements DNS et les certificats pour les URL simples. Si le directeur Skype entreprise Server hérité reste en cours d’utilisation dans la topologie, aucune modification de vos URL simples n’est requise. Si le directeur Skype entreprise Server est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour pour pointer vers l’un des pools de Skype entreprise Server. Cependant, lorsque vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque directeur et serveur frontal pour enregistrer la modification.

## <a name="to-update-the-meet-simple-url"></a>Pour mettre à jour l’URL simple Meet

1. Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud supérieur **Skype entreprise Server**, puis cliquez sur **modifier les propriétés**.
    
2. Sélectionnez **URL simples** dans le volet de gauche, puis sous URL de la **réunion :** sélectionnez l’URL de la réunion, puis cliquez sur **modifier l’URL**.
    
3. Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer. 
    
## <a name="to-update-the-admin-simple-url"></a>Pour mettre à jour l’URL simple Admin

1. Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud supérieur **Skype entreprise Server**, puis cliquez sur **modifier les propriétés**.
    
2. Sélectionnez **URL simples** dans le volet de gauche, puis sous zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour l’accès administratif au panneau de configuration de Skype entreprise Server, puis cliquez sur **OK**.
    
   > [!TIP]
   > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin. L’option la plus simple est https://admin . <em>\<domain\></em> . 
  
## <a name="see-also"></a>Voir aussi

[Configuration DNS requise pour les URL simples dans Skype entreprise Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
