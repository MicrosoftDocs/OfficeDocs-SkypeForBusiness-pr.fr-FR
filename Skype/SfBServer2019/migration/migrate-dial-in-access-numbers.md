---
title: Faire migrer les numéros d’accès entrant
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
description: La migration des numéros d’accès entrant vers Skype entreprise Server 2019 nécessite l’exécution de la cmdlet Move-CsApplicationEndpoint pour migrer les objets contact. Pendant la période de coexistence installation héritée et Skype entreprise Server 2019, les numéros d’accès entrant que vous avez créés dans Skype entreprise Server 2019 se comportent de la même manière que les numéros d’accès entrant que vous créez dans l’installation héritée, comme décrit dans cette section.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752696"
---
# <a name="migrate-dial-in-access-numbers"></a>Faire migrer les numéros d’accès entrant

La migration des numéros d’accès entrant vers Skype entreprise Server 2019 nécessite l’exécution de la cmdlet **Move-CsApplicationEndpoint** pour migrer les objets contact. Pendant la période de coexistence installation héritée et Skype entreprise Server 2019, les numéros d’accès entrant que vous avez créés dans Skype entreprise Server 2019 se comportent de la même manière que les numéros d’accès entrant que vous créez dans l’installation héritée, comme décrit dans cette section. 

Les numéros d’accès entrant que vous avez créés dans l’installation héritée mais qui ont été déplacés vers Skype entreprise Server 2019 ou créés dans Skype entreprise Server 2019 avant, pendant ou après la migration, ont les caractéristiques suivantes :

- N’apparaissent pas sur les invitations aux réunions Office Communications Server 2007 R2 et la page numéro d’accès entrant.

- Apparaissent sur les invitations aux réunions d’installation héritées et la page numéro d’accès entrant.

- Apparaissent sur les invitations aux réunions Skype entreprise Server 2019 et la page numéro d’accès entrant.

- Ne peuvent pas être affichés ni modifiés dans l’outil d’administration Office Communications Server 2007 R2.

- Peuvent être affichés et modifiés dans le panneau de configuration d’installation héritée et dans l’environnement de commande Install Management Shell hérité.

- Peuvent être affichés et modifiés dans le panneau de configuration de Skype entreprise Server 2019 et dans Skype entreprise Server 2019 Management Shell.

- ils peuvent être réordonnés dans la région à l’aide de l’applet de commande Set-CsDialinConferencingAccessNumber avec le paramètre Priority.

Vous devez terminer la migration des numéros d’accès entrant qui pointent vers le pool d’installation hérité avant de désactiver le pool d’installation hérité. Si vous ne terminez pas la migration des numéros d’accès entrant tel que décrit dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.

> [!IMPORTANT]
> Vous devez effectuer cette procédure avant de désactiver le pool d’installation hérité. 

> [!NOTE]
> Nous vous recommandons de déplacer les numéros d’accès entrant lorsque l’utilisation du réseau est faible, au cas où il y aurait une courte période d’interruption de service. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Pour identifier et déplacer les numéros d’accès entrant

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.

2. Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Skype entreprise Server 2019, exécutez la commande suivante à partir de la ligne de commande : 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Ouvrez le panneau de configuration de Skype entreprise Server.

4. Dans la barre de navigation de gauche, cliquez sur **Conférence**.

5. Cliquez sur l’onglet **numéro d’accès entrant** . 

6. Vérifiez qu’il ne reste aucun numéro d’accès entrant pour le pool d’installation hérité à partir duquel vous effectuez la migration.

    > [!NOTE]
    > Lorsque tous les numéros d’accès entrants pointent vers le pool Skype entreprise Server 2019, vous pouvez désactiver le pool d’installation hérité. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Vérifier la migration des numéros d’accès entrant à l’aide du panneau de configuration de Skype entreprise Server

1. À partir d’un compte d’utilisateur affecté au rôle **CsUserAdministrator** ou **CsAdministrator** , ouvrez une session sur un ordinateur de votre déploiement interne. 

2. Ouvrez le panneau de configuration de Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Conférence**.

4. Cliquez sur l’onglet **numéro d’accès entrant** . 

5. Vérifiez que tous les numéros d’accès entrant sont migrés vers le pool hébergé sur Skype entreprise Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Vérifier la migration des numéros d’accès entrant à l’aide de Skype entreprise Server Management Shell

1. Ouvrez Skype entreprise Server Management Shell.

2. Pour renvoyer tous les numéros d’accès de conférence rendez-vous migrés, exécutez la commande suivante à partir de la ligne de commande :

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Vérifiez que tous les numéros d’accès entrant sont migrés vers le pool hébergé sur Skype entreprise Server 2019.


