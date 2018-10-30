---
title: 'Lync Server 2013 : Administration des utilisateurs dans un déploiement hybride'
TOCTitle: Administration des utilisateurs dans un déploiement hybride
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204967(v=OCS.15)
ms:contentKeyID: 49297486
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administration des utilisateurs dans un déploiement Lync Server 2013 hybride

 

_**Dernière rubrique modifiée :** 2014-05-29_

Vous pouvez gérer les paramètres utilisateur et les stratégies pour les utilisateurs migrés vers Lync Online à l’aide des fonctionnalités de gestion des utilisateurs disponibles sur le portail en ligne Microsoft Office 365. Vous devez vous connecter à l’aide d’un compte d’administrateur client pour pouvoir effectuer des tâches d’administration.

## Redéplacement d’utilisateurs vers la version locale

> [!IMPORTANT]  
> Cette section ne s’applique qu’aux utilisateurs créés et activés pour Lync local, puis déplacés d’un déploiement local vers Lync Online. Pour déplacer des utilisateurs créés dans Lync Online (et qui n’ont jamais été activés pour Lync dans un déploiement local), reportez-vous à <a href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Déplacement des utilisateurs de Lync Online vers Lync local dans Lync Server 2013</a>.

  - Pour redéplacer un utilisateur de Lync Online vers Lync local, exécutez l’applet de commande suivante :
    
    ```
    $cred=Get-Credential
    ```
    ```
    Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
    ```

L’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit correspondre à celle du pool où le service de migration hébergée s’exécute, au format suivant :

*Https://\<nom de domaine complet du pool\>/Hosted Migration/hostedmigrationService.svc* . Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.

**Pour déterminer l’URL du service de migration hébergée de votre client Office 365**

1.  Connectez-vous à votre client Office 365 en tant qu’administrateur.

2.  Ouvrez le **Centre d’administration Lync** .

3.  Une fois le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresse jusqu’à **lync.com**. L’URL doit ressembler au format de l’exemple suivant :
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :
    
    `https://admin0a.online.lync.com`

5.  Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
    
    L’URL obtenue, qui est la valeur de **HostedMigrationOverrideUrl**, doit se présenter comme suit :
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

