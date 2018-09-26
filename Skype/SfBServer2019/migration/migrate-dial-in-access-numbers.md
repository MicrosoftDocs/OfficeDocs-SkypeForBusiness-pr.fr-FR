---
title: Migrer les numéros d’accès à distance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migration numéros d’accès à distance à Skype pour Business Server 2019 nécessitent l’exécution de l’applet de commande Move-CsApplicationEndpoint pour migrer les objets de contact. Lors de l’installation héritée et Skype pour la période de coexistence Business Server 2019, les numéros d’accès que vous avez créé dans Skype pour Business Server 2019 agissent comme les numéros d’accès que vous créez dans l’installation héritée, comme décrit dans ce section.
ms.openlocfilehash: 62d2d4f34f109c265a72a92283082601bd92b40b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027724"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrer les numéros d’accès à distance

Migration numéros d’accès à distance à Skype pour Business Server 2019 nécessitent l’exécution de l’applet de commande **Move-CsApplicationEndpoint** pour migrer les objets de contact. Lors de l’installation héritée et Skype pour la période de coexistence Business Server 2019, les numéros d’accès que vous avez créé dans Skype pour Business Server 2019 agissent comme les numéros d’accès que vous créez dans l’installation héritée, comme décrit dans ce section. 
  
Les numéros d’accès que vous avez créé dans hérité installent mais déplacés vers Skype pour Business Server 2019 ou que vous avez créé dans Skype for Business Server 2019 avant, pendant ou après la migration, ont les caractéristiques suivantes :
  
- N’apparaissent pas dans la page de numéro d’accès et les invitations à une réunion Office Communications Server 2007 R2.
    
- Apparaissent sur les invitations aux réunions d’install hérité et de la page de numéro d’accès à distance.
    
- Apparaissent sur Skype pour les invitations à une réunion Business Server 2019 et la page de numéro d’accès à distance.
    
- Ne peuvent pas être affichés ou modifiés dans l’outil d’administration Office Communications Server 2007 R2.
    
- Peuvent être visualisés et modifiés dans l’installation héritée le panneau de configuration et l’installation héritée Management Shell.
    
- Peuvent être visualisés et modifiés dans le Skype pour Business Server 2019 le panneau de configuration et Skype pour Business Server 2019 Management Shell.
    
- Peuvent être séquencés à nouveau dans la zone à l’aide de l’applet de commande Set-CsDialinConferencingAccessNumber avec le paramètre Priority.
    
Vous devez terminer la migration des numéros d’accès à distance qui pointent vers hérité installer pool avant de vous mettre hors service le pool hérité install. Si vous n’effectuez pas la migration des numéros d’accès à distance comme décrit dans la procédure suivante, les appels entrants vers les numéros d’accès échoue.
  
> [!IMPORTANT]
> Vous devez effectuer cette procédure avant de désactiver le pool hérité install. 
  
> [!NOTE]
> Nous vous recommandons de déplacer les numéros d’accès entrant lorsque l’utilisation du réseau est faible, au cas où une courte période d’interruption de service. 
  
## <a name="to-identify-and-move-dial-in-access-numbers"></a>Pour identifier et déplacer les numéros d’accès à distance

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Skype pour Business Server 2019, à partir de la ligne de commande, exécutez : 
    
  ```
  Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
  
  ```

3. Ouvrez le panneau de configuration serveur Business Skype.
    
4. Dans la barre de navigation de gauche, cliquez sur **Conférences**.
    
5. Cliquez sur l’onglet **Numéro d’accès entrant** . 
    
6. Vérifiez qu’il ne reste aucun numéro d’accès à distance pour le pool hérité installer à partir de laquelle vous migrez.
    
    > [!NOTE]
    > Lorsque tous les numéros d’accès à distance pointent vers le Skype pour Business Server 2019 pool, vous pouvez désactiver le pool hérité install. 
  
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Vérifier la migration des numéros d’accès à distance à l’aide de Skype pour Business Server Control Panel

1. À partir d’un compte d’utilisateur auquel est affecté le rôle **CsUserAdministrator** ou **csadministrator** , ouvrez une session n’importe quel ordinateur dans votre déploiement interne. 
    
2. Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférences**.
    
4. Cliquez sur l’onglet **Numéro d’accès entrant** . 
    
5. Vérifiez que tous les numéros d’accès à distance sont migrés vers le pool hébergé sur Skype pour Business Server 2019.
    
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Vérifier la migration des numéros d’accès à distance à l’aide de Skype pour Business Server Management Shell

1. Ouvrez Skype pour Business Server Management Shell.
    
2. Pour retourner tous les numéros d’accès à la conférence rendez-vous migrés, à partir de la ligne de commande exécutée :
    
  ```
  Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
  ```

3. Vérifiez que tous les numéros d’accès à distance sont migrés vers le pool hébergé sur Skype pour Business Server 2019.
    

