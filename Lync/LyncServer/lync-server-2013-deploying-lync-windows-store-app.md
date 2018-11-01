---
title: Déploiement de l’application Lync du Windows Store
TOCTitle: Déploiement de l’application Lync du Windows Store
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ822971(v=OCS.15)
ms:contentKeyID: 53095483
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement de l’application Lync du Windows Store

 

_**Dernière rubrique modifiée :** 2016-12-08_

Avant de mettre l’application Lync du Windows Store à la disposition des utilisateurs, vérifiez que votre déploiement respecte les [Configuration requise de l’application Lync du Windows Store](lync-server-2013-lync-windows-store-app-requirements.md). Pour plus d’informations sur la configuration de Lync Server 2013 pour prendre en charge application Lync du Windows Store, voir l’article du blog NextHop « Lync Server Autodiscover and the Lync Windows Store App » (Découverte automatique de Lync Server et application Lync du Windows Store) à l’adresse [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966). Une fois que votre environnement de serveur est correctement configuré, vous pouvez inviter les utilisateurs à télécharger l’application Lync à partir du Windows Store en recherchant « Lync ».

## Activation de l’authentification multifacteur pour application Lync du Windows Store

Mises à jour cumulatives pour Lync Server 2013 : juin 2013 ajoute la prise en charge de l’authentification multifacteur pour les clients application Lync du Windows Store. Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger l’utilisation d’autres méthodes d’authentification, telles que les cartes à puce ou les codes confidentiels, pour authentifier les utilisateurs externes lorsqu’ils se connectent aux réunions Lync. Pour activer l’authentification multifacteur, vous pouvez déployer le serveur de fédération Active Directory Federation Service (AD FS) et activer l’authentification passive dans Lync Server 2013. Une fois les services AD FS configurés, une page web d’authentification multifacteur AD FS contenant le nom d’utilisateur et le mot de passe de stimulation, ainsi que toutes les méthodes d’authentification supplémentaires que vous avez configurées s’affiche aux utilisateurs externes qui tentent de rejoindre des réunions Lync.

> [!IMPORTANT]  
> Voici quelques considérations importantes si vous prévoyez de configurer les services AD FS pour l’authentification multifacteur pour application Lync du Windows Store :<ul>
> <li><p>Lync Server 2013 avec Mises à jour cumulatives pour Lync Server 2013 : juin 2013 est requis au minimum. Les clients de bureau Lync 2013 ne nécessitent pas Mises à jour cumulatives pour Lync Server 2013 : juin 2013, aussi il peut sembler que l’authentification fonctionne car les clients Lync 2013 peuvent s’authentifier. Le processus d’authentification des clients application Lync du Windows Store échoue toutefois et aucun message d’erreur ou notification ne s’affiche.</p></li>
> <li><p>Le serveur doit être configuré pour que l’authentification passive soit le seul type d’authentification proposé.</p></li>
> <li><p>Si vous utilisez des programmes d’équilibrage de la charge, activez la persistance des cookies sur les programmes d’équilibrage de la charge afin que toutes les demandes du client application Lync du Windows Store soient traitées par le même serveur frontal.</p></li>
> <li><p>Lorsque vous établissez une relation d’approbation de la partie de confiance entre Lync Server et les serveurs AD FS, attribuez une durée de vie de jeton suffisamment longue pour couvrir la durée maximale de vos réunions Lync. Une durée de vie de jeton de 240 minutes est généralement suffisante.</p></li></ul>


**Pour configurer l’authentification multifacteur**

1.  Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, voir le Guide de déploiement des services AD FS 2.0 à l’adresse [http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0x40c)

2.  Créez des certificats pour AD FS. Pour plus d’informations, voir la section « Certificats de serveur de fédération » de l’article « Planifier et déployer AD FS en vue d’une utilisation avec l’authentification unique » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Depuis la ligne de commande Windows PowerShell, exécutez la commande suivante :
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Établissez un partenariat en exécutant la commande suivante :
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Définissez les règles de partie de confiance suivantes :
    
    ```
    $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
    ```
    ```
    Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
    ```
    ```
    Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

## Problèmes connus pouvant empêcher la connexion

## Les date et heure ne sont pas définies correctement sur l’appareil exécutant l’application Lync du Windows Store

Le paramètre d’heure de l’appareil doit être synchronisé avec celui du serveur. Il s’agit d’un aspect particulièrement important pour les appareils tels que Microsoft Surface, et les autres appareils exécutant Windows RT qui ne sont pas joints à un domaine. Pour définir l’heure sur ces appareils de façon automatique à partir d’un serveur de temps, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges sur l’appareil :

    w32tm /resync

## L’application Lync du Windows Store ne peut pas accéder au serveur ou aux services Lync

Il est possible que l’application Lync du Windows Store ne puisse pas accéder au serveur ou aux services Lync via des cartes réseau, telles que des modems USB 4G LTE, lesquels ne sont pas enregistrés auprès de Windows 8 en tant qu’appareils physiques. Il est possible que l’application Lync du Windows Store rencontre ce problème même lorsque les applications de bureau et les navigateurs peuvent accéder aux autres serveurs et sites web.

## L’application Lync du Windows Store ne peut pas se connecter à Lync Server 2010 et un serveur Edge Office Communications Server 2007 R2

Si votre topologie inclut Lync Server 2010 avec un serveur Edge Office Communications Server 2007 R2, vous devrez exécuter la version mise à jour du Générateur de topologies disponible dans la mise à jour cumulative de juillet 2013 pour Lync Server 2010. Les versions antérieures du Générateur de topologies ne créent pas le mappage requis au serveur Edge Office Communications Server 2007, de sorte que les clients Application Lync du Windows Store ne peuvent pas se connecter. Les opérations suivantes sont requises :

1.  Installez la mise à jour cumulative de juillet 2013 pour Lync Server 2010 sur les pools Lync Server 2010 et les directeurs Lync Server 2010.

2.  Mettez à jour la configuration de découverte automatique de Lync pour indiquer que le point d’entrée SIP externe correspond à l’adresse du serveur Edge en procédant comme suit :
    
    1.  Ouvrez Lync Server Management Shell.
    
    2.  Exécutez la commande suivante :
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

## L’application Lync du Windows Store ne peut pas se connecter en raison d’un échec de validation du nom de certificat

Un problème de connexion peut survenir pour les utilisateurs de Office 365 qui n’exécutent pas la dernière version de application Lync du Windows Store. Ce problème survient généralement lorsque plusieurs domaines sont utilisés (par exemple, lorsque l’URI SIP est **userA@domainZ.com** mais que le serveur Edge est **sip.domainX.com**). Pour corriger ce problème, les utilisateurs doivent installer la version la plus récente de application Lync du Windows Store, qui nécessite également Windows 8.1.

## Utilisez les journaux de l’application Lync du Windows Store pour résoudre les problèmes

Vous pouvez utiliser les journaux générés sur l’appareil pour résoudre les problèmes. Les journaux sont stockés dans le dossier suivant :

%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing

Avant de récupérer les journaux d’un utilisateur, vérifiez que la journalisation est activée, puis demandez à l’utilisateur d’enregistrer les journaux afin que les informations stockées en mémoire soient également enregistrées dans des fichiers sur le disque dur.

**Pour activer la journalisation**

1.  Ouvrez l’application Lync du Windows Store sur l’appareil.

2.  Balayez à partir de la droite de l’écran. Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.

3.  Sélectionnez **Paramètres**, puis **Options**, puis définissez **Journaux de diagnostic** sur **Activé**.

4.  Si l’option **Journaux de diagnostic** était désactivée précédemment, vous devez redémarrer Lync en effectuant l’une des opérations suivantes :
    
      - Redémarrez l’appareil.
    
      - Terminez la tâche Lync et lancez à nouveau l’application. Pour terminer la tâche, ouvrez le Gestionnaire des tâches Windows, sélectionnez **Lync**, puis appuyez sur **Arrêter la tâche**. Si Lync n’apparaît pas, appuyez sur **Plus de détails**, puis recherchez Lync sous **Processus en arrière-plan**.

**Pour enregistrer les journaux**

1.  Ouvrez l’application Lync du Windows Store sur l’appareil.

2.  Essayez de vous connecter.

3.  Balayez à partir de la droite de l’écran. Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.

4.  Sélectionnez **Paramètres**, **À propos de**, puis **Enregistrer les journaux**.

