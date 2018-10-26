---
title: 'Lync Server 2013 : Déplacement des utilisateurs vers Lync Online'
TOCTitle: Déplacement des utilisateurs vers Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204969(v=OCS.15)
ms:contentKeyID: 49297497
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement des utilisateurs vers Lync Online dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-05-29_

Avant de commencer la migration d’utilisateurs vers Lync Online, vous devez sauvegarder les données utilisateur associées aux comptes à déplacer. Les données utilisateurs ne sont pas toutes déplacées avec le compte d’utilisateur. Pour plus d’informations, reportez-vous à [Besoins de sauvegarde et de restauration dans Lync Server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md).

## Migration des paramètres utilisateur vers Lync Online

Les paramètres utilisateur sont déplacés en même temps que le compte d’utilisateur. Certains paramètres locaux ne sont pas déplacés avec le compte d’utilisateur.

## Déplacement d’utilisateurs pilotes vers Lync Online

Avant de commencer à déplacer des utilisateurs vers Lync Online, vous souhaiterez peut-être déplacer quelques utilisateurs pilotes pour vous assurer que votre environnement est configuré correctement. Vous pourrez alors vérifier que les fonctionnalités et services Lync fonctionnent comme prévu avant d’essayer de déplacer d’autres utilisateurs.

Pour déplacer un utilisateur local vers votre location Skype Entreprise Online, exécutez les applets de commande suivantes dans Lync Server Management Shell, à l’aide d’informations d’identification d’administrateur correspondant à votre location Microsoft Office 365. Remplacez « nomutilisateur@contoso.com » par les informations correspondant à l’utilisateur que vous souhaitez déplacer.

```
$creds=Get-Credential
```
```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

L’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit correspondre à celle du pool où le service de migration hébergée s’exécute, au format suivant : *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc* .

Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.

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

## Déplacement d’utilisateurs vers Lync Online

Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) avec le paramètre –Filter pour sélectionner les utilisateurs pour lesquels une propriété spécifique est affectée au compte, comme RegistrarPool. Vous pouvez ensuite insérer les utilisateurs renvoyés dans l’applet de commande [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser), comme indiqué dans l’exemple suivant.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Vous pouvez également utiliser le paramètre –OU pour extraire tous les utilisateurs de l’unité d’organisation spécifiée, comme indiqué dans l’exemple suivant.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

## Vérifier les paramètres utilisateur et fonctionnalités de Lync Online

Vous pouvez vérifier que le déplacement d’un utilisateur a réussi des deux manières suivantes :

  - Affichez l’état de l’utilisateur dans le Panneau de configuration de Lync Online. L’indicateur visuel des utilisateurs locaux et en ligne est différent.

  - Exécutez l’applet de commande suivante :
    
        Get-CsUser -Identity

