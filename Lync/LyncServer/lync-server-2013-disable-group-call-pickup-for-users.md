---
title: Désactiver la prise d’appel de groupe pour des utilisateurs
TOCTitle: Désactiver la prise d’appel de groupe pour des utilisateurs
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945638(v=OCS.15)
ms:contentKeyID: 53095465
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Désactiver la prise d’appel de groupe pour des utilisateurs

 

_**Dernière rubrique modifiée :** 2013-01-30_

Appliquez la procédure suivante pour désactiver la fonctionnalité de prise d’appel de groupe pour un utilisateur.

> [!NOTE]  
> Lorsque vous désactiver la prise d’appel de groupe pour un utilisateur, le numéro de groupe de prise d’appel qui a été assigné à cet utilisateur n’est pas conservé. Si vous souhaitez ultérieurement réactiver la prise d’appel de groupe pour cet utilisateur, vous devez réassigner le numéro de groupe de prise d’appel avec le paramètre /enablegrouppickup.

## Pour désactiver la prise d’appel de groupe pour un utilisateur

1.  Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  Sur la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Par exemple :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

## Voir aussi

#### Tâches

[Assigner des numéros de prise d’appel de groupe à des utilisateurs](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Activer la prise d’appel de groupe pour les utilisateurs](lync-server-2013-enable-group-call-pickup-for-users.md)

