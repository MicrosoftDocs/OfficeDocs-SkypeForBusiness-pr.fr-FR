---
title: Configuration de la liste de contacts dynamiques dans Skype Entreprise Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Résumé : Apprenez à activer la fonctionnalité de liste de contacts actives dans le Skype pour client d’entreprise.'
ms.openlocfilehash: f5b5b8f7baa0ce848765a0f2b62aabb118ecb224
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-smart-contacts-list-in-skype-for-business-server"></a>Configuration de la liste de contacts dynamiques dans Skype Entreprise Server
 
**Résumé :** Découvrez comment activer la fonctionnalité de liste de contacts actives dans le Skype pour client d’entreprise.
  
La fonctionnalité de liste de contacts dynamiques permet de remplir automatiquement les listes de contacts pour vos utilisateurs finaux. Lors de la première à l’aide de Skype pour entreprise, votre les utilisateurs verront automatiquement reportez-vous à leur gestionnaire et autres personnes de leur équipe. Cette fonctionnalité est activée par défaut pour les utilisateurs d’Office 365, mais vous devez activer explicitement cette fonctionnalité pour les utilisateurs locaux en configurant le paramètre de stratégie du client.
  
Lors de la configuration cette fonctionnalité, rappelez-vous des points suivants :
  
- Utilisateurs, 13, sont automatiquement ajoutés à la liste de contacts actives dans l’ordre suivant :
    
  1. Responsable
    
  2. Contacts par ordre alphabétique
    
  3. Pairs par ordre alphabétique
    
- La première fois qu’un utilisateur se connecte, le groupe « Mon groupe » est créé. Le groupe est automatiquement rempli avec les personnes dans la relation de groupe Active Directory de l’utilisateur en fonction de l’alias de l’utilisateur dans le champ Gestionnaire de. Notez que les modifications apportées aux membres du groupe AD n’entraînent pas de mises à jour de Mon groupe une fois qu’il a été renseigné initialement. Si un utilisateur supprime un contact ou le groupe, ni le contact ni le groupe n’est recréé. 
    
- Si le marquage automatique est activé, les contacts de la liste sont marqués en cas de changement de statut de présence. Le marquage automatique est activé par défaut, mais vous pouvez choisir de le désactiver. 
    
- Tous les nouveaux utilisateurs du groupe seront informés de leur ajout à la liste de contacts. Les utilisateurs peuvent ajouter manuellement de nouveaux membres au groupe Mon groupe ou à d’autres groupes de leur choix.
    
- Cette fonctionnalité n’est disponible que pour les utilisateurs qui se connectent pour la première fois. Si un utilisateur s’est déjà connecté à partir de n’importe d’un appareil, comme un appareil mobile ou un Mac, la fonctionnalité n’est pas activée pour cet utilisateur.
    
## <a name="configure-smart-contacts-list"></a>Configuration de la liste de contacts dynamiques

Pour activer les fonctionnalités d’une liste de contacts dynamiques pour vos utilisateurs, vous devez suivre la procédure ci-dessous : 
  
- Créer une nouvelle entrée de CsClientPolicy et l’ajouter à la stratégie globale de client. 
    
- Assurez-vous que la recherche dans un carnet d’adresses n’est configurée que pour la recherche web.
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Créez une entrée de stratégie pour activer la liste de contacts dynamiques.

Pour créer une entrée de stratégie pour activer la fonctionnalité de liste de contacts Smart, utilisez l’applet de commande [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option EnableClientAutoPopulateWithTeam comme suit :
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Ensuite, utilisez l’applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications apportées à la stratégie globale, comme suit :
  
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
    
- Confirmez que les informations d’organisation AD sont remplies.
    
- Collecter Skype pour les journaux de client d’entreprise sur un nouvel utilisateur pour une analyse ultérieure.
    
- Confirmez que le Skype pour l’interface utilisateur du client entreprise n’affiche pas un message qu’il ne peut pas se connecter au carnet d’adresses. Pour confirmer la connectivité du carnet d’adresses, effectuez une recherche pour un utilisateur dans le Skype pour la barre de recherche de client entreprise.
    
- S’il existe des problèmes de connexion au carnet d’adresses, utilisez STrace pour collecter des traces HTTPS et HTTPReplay afin d’analyser les traces collectées. Pour plus d’informations, consultez le [blog connexe valider](https://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/).
    
- Les problèmes de réplication AD DS peuvent provoquer des contacts à résolues lorsqu’un utilisateur tout d’abord se connecte à Skype pour les entreprises.
    

