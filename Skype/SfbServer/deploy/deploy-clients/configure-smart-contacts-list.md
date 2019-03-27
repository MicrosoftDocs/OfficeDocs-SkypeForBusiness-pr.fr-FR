---
title: Configurer liste de contacts actives dans Skype pour les clients d’entreprise
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Résumé : Découvrez comment activer la fonctionnalité de liste de contacts actives dans le Skype pour client d’entreprise.'
ms.openlocfilehash: 52de1eb889b1373dc6928c90a9e0e298f467d3fb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896657"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurer liste de contacts actives dans Skype pour les clients d’entreprise

**Résumé :** Découvrez comment activer la fonctionnalité de liste de contacts actives dans le Skype pour client d’entreprise.

La fonctionnalité de liste de contacts dynamiques permet de remplir automatiquement les listes de contacts pour vos utilisateurs finaux. Sur la première à l’aide de Skype pour les entreprises, votre les utilisateurs verront automatiquement constater des leur responsable et autres personnes de leur équipe. Cette fonctionnalité est activée par défaut pour les utilisateurs d’Office 365, mais vous devez explicitement activer cette fonctionnalité pour vos utilisateurs locaux en configurant le paramètre de stratégie de client.

Lors de la configuration de cette fonctionnalité, rappelez-vous des points suivants :

- Jusqu'à 13, les utilisateurs sont automatiquement ajoutés à la liste des contacts actives dans l’ordre suivant :

  1. Responsable

  2. Contacts par ordre alphabétique

  3. Pairs par ordre alphabétique

- La première fois qu’un utilisateur se connecte, le groupe « Mon groupe » est créé. Le groupe est automatiquement renseigné avec les personnes dans une relation de groupe AD de l’utilisateur en fonction de l’alias d’utilisateur renseigné dans le champ Gestionnaire. Notez que les modifications apportées aux membres du groupe AD n’entraînent pas de mises à jour de Mon groupe une fois qu’il a été renseigné initialement. Si un utilisateur supprime un contact ou le groupe, ni le contact ni le groupe n’est recréé. 

- Si le marquage automatique est activé, les contacts de la liste sont marqués en cas de changement de statut de présence. Le marquage automatique est activé par défaut, mais vous pouvez choisir de le désactiver. 

- Tous les nouveaux utilisateurs du groupe seront informés de leur ajout à la liste de contacts. Les utilisateurs peuvent ajouter manuellement de nouveaux membres au groupe Mon groupe ou à d’autres groupes de leur choix.

- Cette fonctionnalité n’est disponible que pour les utilisateurs qui se connectent pour la première fois. Si un utilisateur s’est déjà connecté à partir de n’importe d’un appareil, comme un appareil mobile ou un Mac, la fonctionnalité n’est pas activée pour cet utilisateur.

## <a name="configure-smart-contacts-list"></a>Configuration de la liste de contacts dynamiques

Pour activer les fonctionnalités d’une liste de contacts dynamiques pour vos utilisateurs, vous devez suivre la procédure ci-dessous : 

- Créer une nouvelle entrée CsClientPolicy et l’ajouter à la stratégie globale de clients. 

- Assurez-vous que la recherche dans un carnet d’adresses n’est configurée que pour la recherche web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Créez une entrée de stratégie pour activer la liste de contacts dynamiques.

Pour créer une entrée de stratégie pour activer la fonctionnalité de liste de contacts actives, utilisez l’applet de commande [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option EnableClientAutoPopulateWithTeam comme suit :

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Ensuite, utilisez l’applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications dans la stratégie globale comme suit :

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Vous pouvez éventuellement créer une stratégie pour désactiver le balisage automatique, comme suit :

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Vous devez également définir le paramètre AddressBookAvailability pour la stratégie correspondant à WebSearchOnly. Pour plus d’informations, voir [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Résolution des problèmes

Si la liste de contacts dynamiques ne fonctionne pas comme prévu, vérifiez les points suivants :

- Vérifiez la configuration. 

- Vérifiez que les informations relatives à l’organisation AD sont renseignées.

- Collecter Skype pour les journaux de client d’entreprise sur un nouvel utilisateur pour une analyse approfondie.

- Vérifiez que le Skype pour l’interface utilisateur du client Business n’affiche pas un message il ne peut pas se connecter au carnet d’adresses. Pour vérifier la connectivité du carnet d’adresses, effectuez une recherche pour un utilisateur dans le Skype pour la barre de recherche Business client.

- Problèmes de réplication AD DS peuvent entraîner des contacts pour être résolues lorsqu’un utilisateur tout d’abord se connecte à Skype pour les entreprises.


