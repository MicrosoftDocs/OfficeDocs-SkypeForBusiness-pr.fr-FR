---
title: Configurer la liste de contacts dynamiques dans les clients Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Résumé : Découvrez comment activer la fonctionnalité de liste de contacts dynamiques dans le client Skype entreprise.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776689"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurer la liste de contacts dynamiques dans les clients Skype entreprise

**Résumé :** Découvrez comment activer la fonctionnalité de liste de contacts dynamiques dans le client Skype entreprise.

La fonctionnalité de liste de contacts intelligents autorise le remplissage automatique des listes de contacts pour vos utilisateurs finaux. Lors de la première utilisation de Skype entreprise, vos utilisateurs verront automatiquement leur responsable et d’autres personnes de leur équipe. Cette fonctionnalité est activée par défaut pour les utilisateurs de Microsoft 365 et Office 365, mais vous devez activer explicitement cette fonctionnalité pour vos utilisateurs locaux en configurant le paramètre de stratégie client.

Gardez les points suivants à l’esprit lors de la configuration de cette fonctionnalité :

- Les utilisateurs, jusqu’à 13, sont automatiquement ajoutés à la liste de contacts dynamiques dans l’ordre suivant :

  1. Responsable

  2. Commandes par ordre alphabétique

  3. Pairs par ordre alphabétique

- La première fois qu’un utilisateur se connecte, un nouveau groupe nommé mon groupe est créé. Le groupe est rempli automatiquement avec les personnes appartenant à la relation de groupe Active Directory de l’utilisateur en fonction de l’alias d’utilisateur rempli dans le champ responsable. Notez que les modifications apportées à l’appartenance au groupe AD ne provoquent pas de mises à jour de mon groupe une fois qu’il a été initialement rempli. Si un utilisateur supprime un contact ou le groupe, ni le contact, ni le groupe ne sont recréés. 

- Si le balisage automatique est activé, les contacts de la liste sont balisés pour les modifications de présence. Le balisage automatique est activé par défaut, mais vous pouvez choisir de le désactiver. 

- Tous les nouveaux utilisateurs du groupe sont informés qu’ils ont été ajoutés à la liste des contacts. Les utilisateurs peuvent ajouter manuellement de nouveaux membres à leur groupe ou à d’autres groupes de leur choix.

- Cette fonctionnalité ne fonctionne que pour les utilisateurs qui se connectent pour la première fois. Si un utilisateur s’est déjà connecté à partir de n’importe quel périphérique (y compris, par exemple, un appareil mobile ou un Mac), la fonctionnalité n’est pas activée pour cet utilisateur.

## <a name="configure-smart-contacts-list"></a>Configurer la liste de contacts dynamiques

Pour activer la fonctionnalité de liste de contacts dynamiques pour vos utilisateurs, vous devez effectuer les étapes suivantes : 

- Créer une nouvelle entrée CsClientPolicy et l’ajouter à la stratégie client globale. 

- Assurez-vous que la recherche de carnet d’adresses est configurée pour la recherche sur le Web uniquement.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Créer une entrée de stratégie pour activer la liste de contacts dynamiques

Pour créer une entrée de stratégie pour activer la fonctionnalité de liste de contacts dynamiques, utilisez la cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option enableclientautopopulatewithteam, comme suit :

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Ensuite, utilisez l’applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications apportées à la stratégie globale comme suit :

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Vous pouvez éventuellement créer une stratégie pour désactiver le marquage automatique comme suit :

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Vous devez également définir le paramètre AddressBookAvailability pour la stratégie correspondante sur WebSearchOnly. Pour plus d’informations, consultez la rubrique [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Résolution des problèmes

Si la liste de contacts dynamiques ne fonctionne pas comme prévu, vérifiez les points suivants :

- Validez la configuration. 

- Vérifiez que les informations relatives à l’organisation AD sont remplies.

- Collecter les journaux client Skype entreprise sur un nouvel utilisateur pour une analyse plus poussée.

- Vérifiez que l’interface utilisateur du client Skype entreprise n’affiche pas un message indiquant qu’il ne peut pas se connecter au carnet d’adresses. Pour confirmer la connectivité du carnet d’adresses, effectuez une recherche pour un utilisateur dans la barre de recherche client Skype entreprise.

- Les problèmes de réplication AD DS peuvent empêcher la résolution des contacts lorsqu’un utilisateur se connecte d’abord à Skype entreprise.


