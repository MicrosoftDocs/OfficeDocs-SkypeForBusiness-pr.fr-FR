---
title: Configurer la liste de contacts intelligents dans les clients Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Résumé : Découvrez comment activer la fonctionnalité liste de contacts intelligents dans le client Skype Entreprise.'
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805774"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurer la liste de contacts intelligents dans les clients Skype Entreprise

**Résumé :** Découvrez comment activer la fonctionnalité de liste de contacts intelligents dans le client Skype Entreprise.

La fonctionnalité liste de contacts actifs permet à vos utilisateurs finaux d’avoir une population automatique de listes de contacts. Lors de la première utilisation de Skype Entreprise, vos utilisateurs voient automatiquement leur responsable et d’autres personnes dans leur équipe. Cette fonctionnalité est activée par défaut pour les utilisateurs de Microsoft 365 et Office 365, mais vous devez l’activer explicitement pour vos utilisateurs locaux en configurant le paramètre de stratégie du client.

Gardez à l’esprit les questions suivantes lors de la configuration de cette fonctionnalité :

- Les utilisateurs, jusqu’à 13, sont automatiquement ajoutés à la liste de contacts actifs dans l’ordre suivant :

  1. Manager

  2. Directs par ordre alphabétique

  3. Homologues dans l’ordre alphabétique

- La première fois qu’un utilisateur se connecte, un nouveau groupe, nommé Mon groupe, est créé. Le groupe est automatiquement rempli avec des personnes dans la relation de groupe AD de l’utilisateur en fonction de l’alias utilisateur rempli dans le champ Gestionnaire. Notez que les modifications apportées à l’appartenance au groupe AD n’entraînent pas de mises à jour du groupe Mon groupe une fois qu’il est initialement rempli. Si un utilisateur supprime un contact ou le groupe, ni le contact ni le groupe ne sont re-créés. 

- Si le marquage automatique est allumé, les contacts de la liste sont marqués pour les modifications de présence. Le marquage automatique est désactivé par défaut, mais vous pouvez choisir de le désactiver. 

- Tous les nouveaux utilisateurs du groupe seront informés qu’ils ont été ajoutés à la liste des contacts. Les utilisateurs peuvent ajouter manuellement de nouveaux membres à leur groupe Mon groupe ou à d’autres groupes de leur choix.

- Cette fonctionnalité ne fonctionne que pour les utilisateurs qui se sont signés pour la première fois. Si un utilisateur s’est précédemment connecté à partir d’un appareil, y compris, par exemple, un appareil mobile ou un Mac, la fonctionnalité n’est pas activée pour cet utilisateur.

## <a name="configure-smart-contacts-list"></a>Configuration de la liste de contacts dynamiques

Pour activer la fonctionnalité liste de contacts actifs pour vos utilisateurs, vous devez effectuer les étapes suivantes : 

- Créez une entrée CsClientPolicy et ajoutez-la à la stratégie de client globale. 

- Assurez-vous que la recherche de carnet d’adresses est configurée pour la recherche web uniquement.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Créer une entrée de stratégie pour activer la liste de contacts intelligents

Pour créer une entrée de stratégie afin d’activer la fonctionnalité liste de contacts intelligents, utilisez l’cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option EnableClientAutoPopulateWithTeam comme suit :

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Ensuite, utilisez [l’cmdlet Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications apportées à la stratégie globale comme suit :

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Vous pouvez éventuellement créer une stratégie pour désactiver le marquage automatique comme suit :

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Vous devez également définir le paramètre AddressBookAvailability pour la stratégie correspondante sur WebSearchOnly. Pour plus d’informations, [voir Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Résoudre des problèmes

Si la liste de contacts intelligents ne fonctionne pas comme prévu, vérifiez ce qui suit :

- Validez la configuration. 

- Confirmez que les informations de l’organisation AD sont remplies.

- Collectez les journaux du client Skype Entreprise sur un nouvel utilisateur pour une analyse plus approfondie.

- Confirmez que l’interface utilisateur du client Skype Entreprise n’affiche pas de message pour vous dire qu’elle ne peut pas se connecter au carnet d’adresses. Pour confirmer la connectivité du carnet d’adresses, recherchez un utilisateur dans la barre de recherche du client Skype Entreprise.

- Les problèmes de réplication AD DS peuvent entraîner la non-résolue des contacts lorsqu’un utilisateur se signe pour la première fois dans Skype Entreprise.


