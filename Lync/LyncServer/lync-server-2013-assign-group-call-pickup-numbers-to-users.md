---
title: Assigner des numéros de prise d’appel de groupe à des utilisateurs
TOCTitle: Assigner des numéros de prise d’appel de groupe à des utilisateurs
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945647(v=OCS.15)
ms:contentKeyID: 53095508
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Assigner des numéros de prise d’appel de groupe à des utilisateurs

 

_**Dernière rubrique modifiée :** 2013-01-30_

Après avoir ajouté des numéros de groupes de Prise d’appel de groupe à la table d’orbites de parcage d’appels, vous pouvez assigner ces groupes aux utilisateurs. Utilisez l’outil d’activation des fonctionnalités d’extension secondaire (SEFAUtil) du kit de ressources pour assigner des groupes de prise d’appel à des utilisateurs.

> [!NOTE]  
> Dans un déploiement hybride, n’assignez pas de groupe de Prise d’appel de groupe aux utilisateurs hébergés en ligne. Ceux-ci ne peuvent pas participer à la prise d’appel de groupe. Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.

## Pour assigner un groupe de Prise d’appels de groupe à un utilisateur

1.  Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  Sur la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Par exemple :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## Voir aussi

#### Tâches

[Activer la prise d’appel de groupe pour les utilisateurs](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Désactiver la prise d’appel de groupe pour des utilisateurs](lync-server-2013-disable-group-call-pickup-for-users.md)

