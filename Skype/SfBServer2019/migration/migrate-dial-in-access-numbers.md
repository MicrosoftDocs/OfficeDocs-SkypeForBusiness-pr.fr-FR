---
title: Migration des numéros d’accès entrant
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
description: La migration des numéros d’accès à des appels vers Skype Entreprise Server 2019 nécessite l’exécution Move-CsApplicationEndpoint cmdlet pour migrer les objets contact. Pendant la période d’installation héritée et de coexistence de Skype Entreprise Server 2019, les numéros d’accès à la connexion que vous avez créés dans Skype Entreprise Server 2019 se comportent de la même manière que les numéros d’accès à la connexion que vous créez dans l’installation héritée, comme décrit dans cette section.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752696"
---
# <a name="migrate-dial-in-access-numbers"></a>Migration des numéros d’accès entrant

La migration des numéros d’accès à des appels vers Skype Entreprise Server 2019 nécessite l’exécution de l’cmdlet **Move-CsApplicationEndpoint** pour migrer les objets contact. Pendant la période d’installation héritée et de coexistence de Skype Entreprise Server 2019, les numéros d’accès à la connexion que vous avez créés dans Skype Entreprise Server 2019 se comportent de la même manière que les numéros d’accès à la connexion que vous créez dans l’installation héritée, comme décrit dans cette section. 

Les numéros d’accès à la connexion que vous avez créés dans l’installation héritée, mais que vous avez déplacés vers Skype Entreprise Server 2019, ou que vous avez créés dans Skype Entreprise Server 2019 avant, pendant ou après la migration, ont les caractéristiques suivantes :

- N’apparaissent pas sur les invitations aux réunions Office Communications Server 2007 R2 et la page des numéros d’accès rendez-vous.

- Apparaissent sur les invitations aux réunions d’installation héritées et la page des numéros d’accès rendez-vous.

- Apparaissent sur les invitations aux réunions Skype Entreprise Server 2019 et la page des numéros d’accès rendez-vous.

- Ne peut pas être vu ou modifié dans l’outil d’administration Office Communications Server 2007 R2.

- Peut être vue et modifiée dans le Panneau de contrôle d’installation hérité et dans l’installation héritée de Management Shell.

- Peut être visionnable et modifié dans le Panneau de commande Skype Entreprise Server 2019 et dans Skype Entreprise Server 2019 Management Shell.

- ils peuvent être réordonnés dans la région à l’aide de l’applet de commande Set-CsDialinConferencingAccessNumber avec le paramètre Priority.

Vous devez terminer la migration des numéros d’accès à la connexion qui pointent vers le pool d’installation hérité avant de désaffecter le pool d’installation hérité. Si vous ne terminez pas la migration des numéros d’accès entrant tel que décrit dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.

> [!IMPORTANT]
> Vous devez effectuer cette procédure avant de désaffecter le pool d’installation hérité. 

> [!NOTE]
> Nous vous recommandons de déplacer les numéros d’accès entrant lorsque l’utilisation du réseau est faible, au cas où il y aurait une courte période d’interruption de service. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Pour identifier et déplacer les numéros d’accès entrant

1. Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft Skype Entreprise **Server 2019,** puis sur Skype Entreprise **Server Management Shell.**

2. Pour déplacer chaque numéro d’accès à un pool hébergé sur Skype Entreprise Server 2019, à partir de la ligne de commande, exécutez : 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Ouvrez le Panneau de contrôle Skype Entreprise Server.

4. Dans la barre de navigation de gauche, cliquez sur **Conférence**.

5. Cliquez sur **l’onglet Numéro d’accès** à la connexion. 

6. Vérifiez qu’il ne reste aucun numéro d’accès pour le pool d’installation hérité à partir duquel vous migrez.

    > [!NOTE]
    > Lorsque tous les numéros d’accès à la connexion pointent vers le pool Skype Entreprise Server 2019, vous pouvez ensuite désaffecter le pool d’installation hérité. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Vérifier la migration des numéros d’accès à l’aide du Panneau de contrôle Skype Entreprise Server

1. À partir d’un compte d’utilisateur affecté au rôle **CsUserAdministrator** ou **CsAdministrator,** connectez-vous à n’importe quel ordinateur de votre déploiement interne. 

2. Ouvrez le Panneau de contrôle Skype Entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Conférence**.

4. Cliquez sur **l’onglet Numéro d’accès** à la connexion. 

5. Vérifiez que tous les numéros d’accès sont migrés vers le pool hébergé sur Skype Entreprise Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Vérifier la migration des numéros d’accès à l’aide de Skype Entreprise Server Management Shell

1. Ouvrez Skype Entreprise Server Management Shell.

2. Pour retourner tous les numéros d’accès aux conférences dial-in migrés, à partir de la ligne de commande, exécutez :

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Vérifiez que tous les numéros d’accès sont migrés vers le pool hébergé sur Skype Entreprise Server 2019.


