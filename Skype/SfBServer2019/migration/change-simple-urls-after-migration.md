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
ms.localizationpriority: medium
description: Skype Entreprise Server prend en charge les URL simples.
ms.openlocfilehash: 8bbbb55262e353ff66adeaca194e7060e3ff7ca5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618310"
---
# <a name="change-simple-urls-after-migration"></a>Modification des URL simples après la migration

Skype Entreprise Server prend en charge trois URL simples :
  
- **Meet** qui est l’URL de réunion de base pour toutes les conférences dans le site ou l’organisation. Avec l’URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre, à communiquer et à distribuer. 
    
- **Dial-in** qui permet d’accéder à la page web Paramètres de conférence rendez-vous. L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. 
    
- **L’administrateur** permet un accès rapide au Panneau de Skype Entreprise Server de contrôle. L’URL simple d’administration est interne à votre organisation. 
    
Après avoir migré vers Skype Entreprise Server, vous devez connaître l’impact de la modification sur vos enregistrements et certificats DNS pour les URL simples. Si le directeur Skype Entreprise Server hérité reste en cours d’utilisation dans la topologie, aucune modification de vos URL simples n’est requise. Si le directeur Skype Entreprise Server est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour pour pointer vers l’un des pools Skype Entreprise Server. Cependant, lorsque vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque directeur et serveur frontal pour enregistrer la modification.

## <a name="to-update-the-meet-simple-url"></a>Pour mettre à jour l’URL simple Meet

1. Dans le Générateur de topologie, cliquez avec le bouton droit sur le **nœud Skype Entreprise Server,** puis cliquez sur **Modifier les propriétés.**
    
2. Sélectionnez **URL simples** dans le volet  gauche, puis sous URL de réunion : sélectionnez l’URL de réunion, puis cliquez sur **Modifier l’URL.**
    
3. Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer. 
    
## <a name="to-update-the-admin-simple-url"></a>Pour mettre à jour l’URL simple Admin

1. Dans le Générateur de topologie, cliquez avec le bouton droit sur le **nœud Skype Entreprise Server,** puis cliquez sur **Modifier les propriétés.**
    
2. Sélectionnez **URL** simples dans le volet gauche, puis sous la zone **URL** d’accès administratif, entrez l’URL simple que vous souhaitez pour l’accès administratif au Panneau de Skype Entreprise Server, puis cliquez sur **OK**.
    
   > [!TIP]
   > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin. L’option la plus simple https://admin est ... <em>\<domain\></em> 
  
## <a name="see-also"></a>Voir aussi

[DNS requirements for simple URLs in Skype Entreprise Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
