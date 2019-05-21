---
title: Configurer une liste de contacts dynamiques dans les clients Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Résumé: Découvrez comment activer la fonctionnalité liste de contacts intelligents dans le client Skype entreprise.'
ms.openlocfilehash: 0deb90293ddf4f1a6627eb4bff86d7d8eb0ae5c9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286382"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurer une liste de contacts dynamiques dans les clients Skype entreprise

**Résumé:** Découvrez comment activer la fonctionnalité liste de contacts dynamiques dans le client Skype entreprise.

La fonctionnalité de liste de contacts dynamiques permet de remplir automatiquement les listes de contacts pour vos utilisateurs finaux. Dès lors que vous utilisez Skype entreprise pour la première fois, vos utilisateurs voient automatiquement le responsable et les autres membres de leur équipe. Cette fonctionnalité est activée par défaut pour les utilisateurs d’Office 365, mais vous devez activer explicitement cette fonctionnalité pour vos utilisateurs locaux en configurant le paramètre de stratégie client.

Lors de la configuration de cette fonctionnalité, rappelez-vous des points suivants :

- Les utilisateurs de plus de 13 ans sont automatiquement ajoutés à la liste des contacts dynamiques dans l’ordre suivant:

  1. Responsable

  2. Contacts par ordre alphabétique

  3. Pairs par ordre alphabétique

- La première fois qu’un utilisateur se connecte, le groupe « Mon groupe » est créé. Le groupe est automatiquement rempli de personnes dans la relation de groupe publicitaire de l’utilisateur en fonction de l’alias d’utilisateur rempli dans le champ responsable. Notez que les modifications apportées aux membres du groupe AD n’entraînent pas de mises à jour de Mon groupe une fois qu’il a été renseigné initialement. Si un utilisateur supprime un contact ou le groupe, ni le contact ni le groupe n’est recréé. 

- Si le marquage automatique est activé, les contacts de la liste sont marqués en cas de changement de statut de présence. Le marquage automatique est activé par défaut, mais vous pouvez choisir de le désactiver. 

- Tous les nouveaux utilisateurs du groupe seront informés de leur ajout à la liste de contacts. Les utilisateurs peuvent ajouter manuellement de nouveaux membres au groupe Mon groupe ou à d’autres groupes de leur choix.

- Cette fonctionnalité n’est disponible que pour les utilisateurs qui se connectent pour la première fois. Si un utilisateur s’est déjà connecté à partir de n’importe d’un appareil, comme un appareil mobile ou un Mac, la fonctionnalité n’est pas activée pour cet utilisateur.

## <a name="configure-smart-contacts-list"></a>Configuration de la liste de contacts dynamiques

Pour activer les fonctionnalités d’une liste de contacts dynamiques pour vos utilisateurs, vous devez suivre la procédure ci-dessous : 

- Créez une nouvelle entrée CsClientPolicy et ajoutez-la à la stratégie client globale. 

- Assurez-vous que la recherche dans un carnet d’adresses n’est configurée que pour la recherche web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Créez une entrée de stratégie pour activer la liste de contacts dynamiques.

Pour créer une entrée de stratégie permettant d’activer la fonctionnalité liste de contacts dynamiques, utilisez l’applet [de commande New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option EnableClientAutoPopulateWithTeam comme suit:

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Ensuite, utilisez l’applet de passe [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications apportées à la stratégie globale comme suit:

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Vous pouvez éventuellement créer une stratégie pour désactiver le balisage automatique, comme suit :

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Vous devez également définir le paramètre AddressBookAvailability pour la stratégie correspondant à WebSearchOnly. Pour plus d’informations, consultez la rubrique [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Résolution des problèmes

Si la liste de contacts dynamiques ne fonctionne pas comme prévu, vérifiez les points suivants :

- Vérifiez la configuration. 

- Vérifiez que les informations relatives à l’organisation AD sont renseignées.

- Pour une analyse plus approfondie, le client Skype entreprise enregistre une connexion à un nouvel utilisateur.

- Confirmez que l’interface utilisateur du client Skype entreprise n’affiche aucun message indiquant qu’il n’est pas possible de se connecter au carnet d’adresses. Pour confirmer la connectivité du carnet d’adresses, recherchez un utilisateur dans la barre de recherche du client Skype entreprise.

- Les problèmes de réplication AD DS peuvent entraîner la non-gestion des contacts lorsque l’utilisateur se connecte à Skype entreprise pour la première fois.


