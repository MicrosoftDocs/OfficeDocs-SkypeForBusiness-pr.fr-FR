---
title: Modification des URL simples après la migration
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
description: Skype entreprise Server prend en charge des URL simples.
ms.openlocfilehash: ab820c1b24eb9b2e8befc85a34e82d068c9083ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813882"
---
# <a name="change-simple-urls-after-migration"></a>Modification des URL simples après la migration

Skype entreprise Server prend en charge trois URL simples :
  
- La **fonction réunion** est utilisée comme URL de base pour toutes les conférences du site ou de l’organisation. Avec l’URL de la réunion, vous pouvez facilement comprendre les liens permettant de participer à des réunions, et facilement communiquer et diffuser. 
    
- Le rendez **-** vous permet d’accéder à la page Web des paramètres de conférence rendez-vous. L’URL d’accès à un rendez-vous est incluse dans toutes les invitations à une réunion de sorte que les utilisateurs qui souhaitent se connecter à la réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires. 
    
- L' **administrateur** permet d’accéder rapidement au panneau de configuration Skype entreprise Server. L’URL simple Admin est interne à votre organisation. 
    
Après la migration vers Skype entreprise Server, vous devez tenir compte des différences entre les enregistrements DNS et les certificats pour des URL simples. Si le directeur Skype entreprise Server hérité reste utilisé dans la topologie, aucune modification de vos URL simples n’est requise. Si le directeur de Skype entreprise Server est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour de manière à ce qu’ils pointent vers l’une des listes de serveurs Skype entreprise. Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque réalisateur et serveur frontal pour enregistrer la modification.

## <a name="to-update-the-meet-simple-url"></a>Pour mettre à jour l’URL de réunion simple

1. Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Skype entreprise Server**, puis cliquez sur **modifier les propriétés**.
    
2. Sélectionnez **URL simples** dans le volet gauche, puis sous **URL de la réunion :** sélectionnez l’URL de la réunion, puis cliquez sur **modifier l’URL**.
    
3. Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée. 
    
## <a name="to-update-the-admin-simple-url"></a>Pour mettre à jour l’URL simple d’administration

1. Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Skype entreprise Server**, puis cliquez sur **modifier les propriétés**.
    
2. Sélectionnez **URL simples** dans le volet gauche, puis sous **URL d’accès administratif** , entrez l’URL que vous voulez pour l’accès administratif à Skype entreprise Server panneau de configuration, puis cliquez sur **OK**.
    
   > [!TIP]
   > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration. L’option la plus simple https://adminest. <em>Domain (domaine\>). \<</em> 
  
## <a name="see-also"></a>Voir aussi

[Configuration DNS requise pour les URL simples dans Skype entreprise Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
