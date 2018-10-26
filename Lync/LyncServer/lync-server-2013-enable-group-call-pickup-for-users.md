---
title: Activer la prise d’appel de groupe pour les utilisateurs
TOCTitle: Activer la prise d’appel de groupe pour les utilisateurs
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945620(v=OCS.15)
ms:contentKeyID: 53095373
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activer la prise d’appel de groupe pour les utilisateurs

 

_**Dernière rubrique modifiée :** 2013-01-30_

Utilisez l’outil de kit de ressources SEFAUtil pour activer la prise d’appel de groupe pour les utilisateurs. Les utilisateurs doivent se voir attribuer un numéro de groupe de type GroupPickup dans la table des numéros d’appel parqué pour bénéficier de la prise d’appel de groupe. Vous affectez un numéro de groupe de prise d’appel et activez la prise d’appel de groupe simultanément à l’aide du paramètre /enablegrouppickup quand vous exécutez l’utilitaire SEFAUtil.exe.

## Pour activer la prise d’appel de groupe pour un utilisateur

1.  Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil en tant qu’administrateur.

2.  Sur la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Exemple :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## Voir aussi

#### Tâches

[Assigner des numéros de prise d’appel de groupe à des utilisateurs](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Désactiver la prise d’appel de groupe pour des utilisateurs](lync-server-2013-disable-group-call-pickup-for-users.md)

