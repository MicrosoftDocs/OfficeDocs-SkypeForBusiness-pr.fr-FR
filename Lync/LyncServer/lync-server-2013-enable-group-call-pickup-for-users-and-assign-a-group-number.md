---
title: "Activer la prise d’appel de gr. pour des ut. et assigner un numéro de groupe"
TOCtitle: "Activer la prise d’appel de gr. pour des ut. et assigner un numéro de groupe"
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945650(v=OCS.15)
ms:contentKeyID: 53095518
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activer la prise d’appel de groupe pour des utilisateurs et assigner un numéro de groupe

 

_**Dernière rubrique modifiée :** 2013-01-30_

Après avoir ajouté des numéros de groupes de prise d’appel à la table d’orbites de parcage d’appels, vous assignez ces numéros de groupes aux utilisateurs et vous activez la Prise d’appel de groupe pour eux. Utilisez l’outil d’activation des fonctionnalités d’extension secondaire (SEFAUtil) du kit de ressources pour assigner des numéros de groupes et activer la Prise d’appel de groupe.

> [!NOTE]  
> Dans un déploiement hybride, n’assignez pas de groupe de Prise d’appel de groupe aux utilisateurs hébergés en ligne. Ceux-ci ne peuvent pas participer à la prise d’appel de groupe. Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.

## Pour assigner un numéro de groupe et activer la Prise d’appel de groupe pour un utilisateur

1.  Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  Sur la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Par exemple, pour assigner le numéro de groupe 199 à un utilisateur, procédez comme suit :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

## Voir aussi

#### Tâches

[Désactiver la prise d’appel de groupe pour des utilisateurs](lync-server-2013-disable-group-call-pickup-for-users.md)

