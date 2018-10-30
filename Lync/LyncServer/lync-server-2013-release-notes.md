---
title: Notes de publication de Lync Server 2013
TOCTitle: Notes de publication
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205120(v=OCS.15)
ms:contentKeyID: 49298383
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Notes de publication de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Bienvenue dans les Notes de publication de Lync Server 2013. Consultez ce fichier afin d’en savoir plus sur les problèmes connus liés à Lync Server 2013.

## À propos de ce document

Ce document contient des informations importantes que vous devez connaître avant de déployer et d’utiliser Lync Server 2013. Pour plus d’informations sur Lync Server 2013, reportez-vous à la documentation de [Microsoft Lync Server 2013](microsoft-lync-server-2013.md).

Ce document contient les sections suivantes :

  - Client Skype Entreprise 2015

  - Lync Server

  - Installation

  - Mobilité

  - Conférence

  - Voix Entreprise

  - Présence

  - application Response Group, application de parcage d’appel et prise d’appel de groupe

  - Panneau de configuration de Lync Server, générateur de topologie et Outil de planification

  - Localisation

  - Copyright

## Client Skype Entreprise 2015

## Échec du transfert d’un fichier dans un message instantané si le fichier est ouvert dans une autre application (1920369)

**Problème :**

Si vous tentez de transférer un fichier, par exemple un document Word, en l’incluant dans un message instantané destiné à un autre utilisateur Skype Entreprise, le transfert du fichier semble aboutir alors que ce n'est pas le cas. Une icône représentant le type de fichier s’affiche dans le client Skype Entreprise, mais le destinataire ne peut pas l’ouvrir. Aucun message d’erreur ne s’affiche pour vous informer que le transfert a échoué.

**Solution de contournement :**

Pour contourner ce problème, fermez le fichier ouvert ou l’application dans laquelle il est ouvert, puis tentez de transférer le fichier dans un message instantané.

## Lync Server

## En cas d’échec de la réplication des données du service de stockage Lync Server, les administrateurs devront vérifier les compteurs de performances pour déterminer si des éléments de la file d’attente du service de stockage sont obsolètes (3225121)

**Problème :**

Le service de stockage de Lync Server utilise Windows Fabric pour la réplication. Si des données sont supprimées sur un serveur frontal principal, mais que la suppression sur un serveur frontal secondaire échoue, par exemple, en cas d’erreur ou d’arrêt inattendu sur le serveur frontal, des données peuvent être « oubliées » et devenir orphelines. Ces données orphelines peuvent entraîner une dégradation des performances et un gaspillage de l’espace disque.

**Solution de contournement :**

Pour contourner ce problème, si les événements LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) et LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) sont générés dans le journal des événements, les administrateurs doivent vérifier le compteur de performance sur le serveur frontal sous **LS:LYSS - Storage Service API** nommé **LYSS - Current number of Storage Service stale queue items**. Si ce compteur de performance a une valeur élevée (par exemple, supérieure à 50 000), l’administrateur doit exécuter l’outil CleanuUpStorageServiceData.exe du Kit de ressources de Lync Server 2013, qui supprimera toutes les données orphelines du pool. Pour plus d’informations sur cet outil, reportez-vous à la documentation du Kit de ressources de Lync Server 2013.

## Chaque fois que la configuration des adresses IP est modifiée pour un serveur ou un pool, les services Lync Server doivent être redémarrés (3212447)

**Problème :**

Lorsque la configuration des adresses IP est modifiée pour un déploiement de Lync Server 2013 (par exemple, lors du passage d’IPv4 à Double pile ou de Double pile à IPv6), certains composants de serveur ne sont informés de la modification que lors du redémarrage des services.

**Solution de contournement :**

Pour contourner ce problème, redémarrez les services Lync Server après avoir modifié la configuration des adresses IP pour le déploiement. Pour cela, exécutez les applets de commande suivantes dans Lync Server Management Shell :

```
Stop-CsWindowsService -graceful
```
```
Start-CsWindowsService
```

## L’applet de commande de transaction synthétique de conférence rendez-vous n’est plus disponible dans le Pack de gestion de Lync Server 2013(3212342)

**Problème :**

L’applet de commande de transaction synthétique de conférence rendez-vous **Test-CsDialInConferencing** n’est plus disponible dans le Pack de gestion de Lync Server 2013.

**Solution de contournement :**

L’utilisation de l’applet de commande de transaction synthétique de conférence rendez-vous **Test-CsDialInConferencing** est prise en charge uniquement en interne, au sein d’une entreprise.

Les administrateurs peuvent continuer d’utiliser cette applet de commande dans Lync Server Management Shell pour l’identification et de résolution des problèmes. Si nécessaire, une entreprise peut développer un pack de gestion privé pour exécuter l’applet de commande en interne.

## Le service de journalisation centralisée s’arrête si le trafic réseau est perturbé pendant la copie de fichiers journaux vers un partage réseau (3212464)

**Problème :**

Lorsque le service de journalisation centralisée est configuré de façon à utiliser un chemin d’accès réseau (la valeur du paramètre CacheFileNetworkFolder de l’applet de commande **Get-CsClsConfiguration** est un chemin d’accès UNC valide), les fichiers journaux mis en cache sont copiés vers le partage réseau. Si le trafic réseau est perturbé durant la copie des fichiers, une exception se produit et le service de journalisation centralisée est arrêté.

Ce service étant configuré de façon à redémarrer automatiquement jusqu’à trois fois, il récupèrera suite aux trois premières exceptions.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème. Pour identifier le problème, surveillez le journal des événements pour voir s’il contient l’ID d’événement 7031 du « Gestionnaire de contrôle des services » consigné lorsque le service « Agent du Service de journalisation centralisée de Lync Server » a été arrêté de manière inattendue. Si cela se produit plus de trois fois, redémarrez manuellement le service à l’aide de l’applet de commande **Start-CsWindowService**.

## Des éléments de la file d’attente du service de stockage doivent être importés manuellement (3211368)

**Problème :**

Lync Server 2013 stocke les données relatives aux conférences et à la messagerie instantanée, telles que les messages archivés et l’enregistrement des détails des appels (CDR), sur une base de données sur chaque serveur frontal. Les données sont stockées dans la base de données durant leur traitement, avant d’être remises à la destination prévue. Pour améliorer les performances, Lync Server 2013 exporte régulièrement à partir de la base de données locale les éléments de la file d’attente qui n’ont toujours pas été traités après un certain délai, et il les enregistre dans le magasin de fichiers. Si celui-ci est indisponible, les éléments sont stockés sur chaque serveur frontal. La même opération se produit afin d’éviter toute perte de données durant le basculement de pool.

Durant l’opération d’exportation, le service de stockage de Lync Server enregistre chaque étape dans le journal des événements avec les ID d’événements 32075 (démarrage d’une opération de vidage complète), 32076 (vidage complet terminé), 32082 (démarrage du vidage de niveau maintenance), 32083 (vidage de niveau maintenance terminé) et 32089 (vidage effectué à cause du remplissage de la base de données). Ces données ne seront pas réimportées automatiquement dans le système afin d’être traitées et remises à leur destination finale ( SQL Server ou Exchange Server).

**Solution de contournement :**

Pour importer les données dans le système, les administrateurs doivent utiliser l’outil ImportStorageServiceData du Kit de ressources de Lync Server, qui rajoutera les données au système en vue de leur traitement et de leur remise à leur destination finale.

## Les recherches d’interrogation web du carnet d’adresses échouent si la valeur par défaut de UseNormalizationRules est changée en False (3175514)

**Problème :**

Si la valeur par défaut de UseNormalizationRules est changée en False, les recherches d’interrogation web du carnet d’adresses échouent. Une fois la valeur par défaut modifiée, les utilisateurs du client Lync ne pourront pas utiliser l’interrogation web du carnet d’adresses Lync pour rechercher des utilisateurs.

**Solution de contournement :**

Si la valeur False est affectée comme valeur par défaut à UseNormalizationRules de sorte que les utilisateurs puissent utiliser des numéros de téléphone tels que définis dans les services de domaine Active Directory sans que Lync Server 2013 n’applique des règles de normalisation, vous pouvez contourner ce problème en procédant comme suit :

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Effectuez l’une des actions suivantes :
    
      - Si votre déploiement comprend uniquement des serveurs Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour affecter la valeur True à UseNormalizationRules et IgnoreGenericRules :
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si votre déploiement comprend une combinaison de Lync Server 2013 et de Lync Server 2010 ou d’Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 de la topologie :
      ```
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
      ```
3.  Attendez que le réplication CMS ait lieu sur tous les pools.

4.  Modifiez le fichier de règles de normalisation téléphonique de votre déploiement afin d’effacer le contenu. Ce fichier se trouve sur le partage réseau de chaque pool Lync Server 2013. S’il est absent, créez un fichier vide nommé « Company\_Phone\_Number\_Normalization\_Rules.txt ».

5.  Attendez quelques minutes que tous les pools frontaux aient lu les nouveaux fichiers.

6.  Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 de votre déploiement.
    
        Update-csAddressBook

## L’événement d’erreur 21054 de serveur de carnet d’adresses est généré une fois par jour pour chaque pool Lync 2013 (3195918)

**Problème :**

Le serveur de carnet d’adresses de Lync Server 2013 génère l’événement d’erreur 21054 une fois par jour lors de l’exécution de la maintenance quotidienne. Cette erreur est également générée chaque fois qu’un administrateur exécute l’applet de commande **Update-csAddressBook**, même quand la mise à jour réussit. Cependant, cet événement d’erreur peut être ignoré sans risque lorsque la mise à jour réussit.

**Solution de contournement :**

Lorsque vous rencontrez cet événement d’erreur, exécutez l’applet de commande suivante :

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Si l’applet de commande signale qu’il n’y a aucun objet abandonné ou non indexé, l’événement d’erreur 21054 peut être ignoré sans risque.

Par ailleurs, l’indicateur d’intégrité de clé « Utilisateurs de carnet d’adresses correctement indexés » doit être désactivé dans System Center Operations Manager.

## Des demandes peuvent échouer quand le protocole IPv6 est configuré sur un pool Edge (3205810)

**Problème :**

Lorsque le protocole IPv6 est configuré sur un pool Edge, certaines demandes envoyées au pool Edge peuvent échouer.

**Solution de contournement :**

Pour contourner ce problème, ne configurez pas de pool Edge avec le protocole IPv6.

## L’applet de commande invoke-csPoolFailback peut échouer durant une restauration de pool (3206153)

**Problème :**

Lors d’une tentative de restauration de pool, l’applet de commande **invoke-csPoolFailback** peut échouer et renvoyer l’erreur « Désolé... En dépit de plusieurs tentatives, nous n’avons pas pu effectuer le processus d’hydration. ».

**Solution de contournement :**

Pour contourner ce problème, réexécutez l’applet de commande et attendez qu’elle réussisse. Notez que le processus de restauration peut prendre plusieurs minutes (jusqu’à 60 minutes pour un pool de 20 000 utilisateurs).

## Une perte de données peut se produire lorsque vous ajoutez un serveur frontal à un pool déjà établi (3015990) – Hybride, Skype Entreprise Online

**Problème :**

Ce problème peut se présenter dans un environnement dans lequel un pool comporte plus d’un seul serveur frontal et que vous redémarrez l’un des serveurs frontaux ou que vous ajoutez un nouveau serveur frontal qui ne faisait pas partie du pool précédemment.

Les utilisateurs dont les données sont en cours d’archivage peuvent constater une perte de données jusqu’à ce qu’une distribution stable de l’archivage des données soit établie pour le pool. Cette période de perte de données potentielle est limitée à 15 minutes pour les conversations de personne à personne et à 30 minutes pour les conférences.

**Solution de contournement :**

Lorsque vous effectuez la maintenance, au lieu de démarrer les serveurs frontaux dans le pool un par un, vous devez faire basculer le pool vers un autre pool, puis effectuer les tâches de maintenance sur les serveurs. Vous pouvez également rendre le service indisponible avant d’effectuer les tâches de maintenance, puis rétablir la disponibilité une fois la maintenance terminée.

## Les administrateurs ne peuvent pas obtenir le nombre de licences à l’aide de l’applet de commande Get-CsClientAccessLicense (3012255)

**Problème :**

Les administrateurs ne peuvent pas obtenir d’informations correctes relatives à l’utilisation des licences client à l’aide de l’applet de commande **Get-CsClientAccessLicense**.

**Solution de contournement :**

Pour vérifier le type de licence serveur, vous pouvez exécuter l’applet de commande **Get-CsService** pour extraire les noms de domaine complets de toutes les bases de données. Si le nom de domaine complet du serveur frontal est identique à celui de la base de données principale, cela signifie qu’il s’agit d’une licence Standard Edition. Dans le cas contraire, il s’agit d’une licence Enterprise Edition.

## Le nombre de titulaires de licences client signalé est incorrect (3010175)

**Problème :**

Lors de la détermination du nombre de licences client, vous pouvez rencontrer les conditions suivantes :

1.  **Nombre de licences incorrect pour les utilisateurs mobiles**
    
    Le nombre de licences est basé sur le nombre d’adresses IP uniques pour les utilisateurs de périphériques mobiles. Le nombre de licence sera limité des manières suivantes :
    
      - Le nombre de licences est surévalué si l’adresse IP de l’utilisateur change durant les sessions Lync. Cela peut se produire quand un utilisateur se connecte à Lync Server depuis plusieurs emplacements avec un client de bureau.
    
      - Le nombre de licences est sous-évalué si un utilisateur se connecte avec un client mobile, car l’adresse IP de l’appareil ne peut pas être déterminée.

2.  **Les licences sont comptabilisées deux fois pour les appels RTC (réseau téléphonique commuté) vers le client Lync, les appels de clients Lync vers des lignes RTC et les appels Lync transférés à des lignes RTC**
    
    Dans les scénarios suivants, deux licences supplémentaires sont comptabilisées (au lieu d’une seule) car le numéro de téléphone et l’utilisateur Lync sont tous deux comptés afin de déterminer le nombre de licences utilisés. Pour obtenir des données de licence correctes, supprimez manuellement les licences générées par un numéro de téléphone.
    
      - Un appel téléphonique RTC vers Lync
    
      - Un appel Lync vers une ligne RTC
    
      - Un appel RTC vers Lync, qui est ensuite transféré par Lync à une ligne RTC. L’une des lignes RTC est comptabilisée.

3.  **Aucune licence n’est comptabilisée pour un téléphone Lync connecté**
    
    Lorsqu’un utilisateur utilise un téléphone certifié Lync, si le téléphone se connecte et reste connecté (auquel cas son statut de connexion est conservé), le téléphone n’est pas comptabilisé comme utilisant une licence si l’interrogation de licence a lieu après la connexion du téléphone.

4.  **Licences comptabilisées pour les téléphones RTC prenant part à des conférences**
    
    Lorsqu’un utilisateur prend part à une conférence avec un téléphone RTC, une licence est comptabilisée de manière incorrecte pour la participation à la conférence. Cependant, aucune licence n’est nécessaire pour prendre part à une conférence avec un téléphone RTC.

**Solution de contournement :**

1.  **Nombre de licences incorrect pour les utilisateurs mobiles**
    
      - Vous pouvez identifier manuellement les adresses IP qui appartiennent au même périphérique, puis supprimer l’une d’entre elles dans le nombre de licences.
    
      - Il n’existe aucune solution de contournement à ce problème dans le cas des appareils mobiles se connectant avec le client Lync.

2.  **Les licences sont comptabilisées deux fois pour les appels RTC vers le client Lync, les appels de clients Lync vers des lignes RTC et les appels Lync transférés à des lignes RTC**
    
    Vous devez identifier manuellement le numéro de téléphone RTC et supprimer la licence générée pour ce numéro.

3.  **Aucune licence n’est comptabilisée pour un téléphone Lync connecté**
    
    Vous pouvez configurer le téléphone Lync pour qu’il se déconnecte puis se reconnecte à intervalles réguliers (par exemple, tous les trois mois).

4.  **Licences comptabilisées pour les téléphones RTC prenant part à des conférences**
    
    Vous pouvez identifier manuellement le numéro de téléphone RTC utilisé pour prendre part à la conférence et supprimer la licence générée par ce numéro de téléphone.

## Le Panneau de configuration Lync Server cesse de fonctionner dans un environnement VMware après la mise à niveau vers Silverlight 5 (3010077)

**Problème :**

Si vous utilisez le Panneau de configuration Lync Server dans un environnement VMware, le Panneau de configuration Lync Server peut cesser de fonctionner après la mise à niveau de Microsoft Silverlight vers la version 5.

**Solution de contournement :**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Désinstallez Silverlight 5 et installez Silverlight 4 depuis [http://go.microsoft.com/fwlink/p/?LinkID=149156](http://go.microsoft.com/fwlink/p/?linkid=149156).

  - Accédez au Panneau de configuration Lync Server à partir d’un ordinateur qui n’est pas un ordinateur virtuel VMware.
    
    Pour cela, vous pouvez démarrer le Panneau de configuration Lync Server à partir du menu **Démarrer** de Windows sur le serveur, si les outils d’administration de Lync Server sont installés sur l’ordinateur.
    
    Vous pouvez également accéder au Panneau de configuration Lync Server à l’aide d’un navigateur web. L’URL sera semblable à https://\<nom\_domaine\_complet\_pool\_frontal\>/cscp.

## Les informations utilisateur dans le service de carnet d’adresses ne sont pas mises à jour après la modification du nom unique de l’utilisateur dans Active Directory (3211549)

**Problème :**

Si le nom unique (également appelé DN) est modifié dans services de domaine Active Directory, les autres modifications ne seront pas mises à jour dans le Service de carnet d’adresses (ABS). Cela n’affecte pas la connexion ou la présence de l’utilisateur, mais empêchera toute communication pour l’utilisateur si l’adresse SIP est également modifiée, car les recherches renverront une adresse IP obsolète.

**Solution de contournement :**

Pour contourner ce problème, ne modifiez pas le nom unique de l’utilisateur. Si vous rétablissez la valeur précédente du nom unique de l’utilisateur, les mises à jour seront reflétées dans le service de carnet d’adresses.

## Installation

## Utiliser des caractères non-ASCII peut provoquer l’échec du démarrage du serveur Lync

**Problème :**

L’installaton échouera si le nom du dossier de destination inclut des caractères non-ASCII (y compris des caractères UNICODE, UTF-8 et UTF-16, ou un jeu de caractères codés sur 2 octets \[DBCS\]). En outre, elle peut aboutir mais le serveur ne démarrera pas si les noms suivants contiennent des caractères non-ASCII :

  - Nom de l’ordinateur

  - Nom du domaine

  - Nom utilisateur

  - Nom SIP utilisateur

  - Nom du compte de service

**Solution de contournement :**

Le correctif logiciel au problème « Un endommagement de segment se produit quand un module appelle la méthode

## Le correctif logiciel au problème « Un segment est altéré lorsqu’un module appelle la méthode InsertEntityBody dans les services Internet (IIS) 7.5 » doit être installé avant Lync Server 2013

**Problème :**

Le correctif logiciel au problème « Un endommagement de segment se produit quand un module appelle la méthode InsertEntityBody dans les services Internet (IIS) 7.5 » ( <http://go.microsoft.com/fwlink/?linkid=268602>) décrit dans l’article 264886 de la Base de connaissances Microsoft ( <http://go.microsoft.com/fwlink/?linkid=268603>), doit être installé avant de procéder à l’installation de Lync Server 2013.

**Solution de contournement :**

Téléchargez et installez le correctif logiciel à partir du Centre de téléchargement Microsoft à l’adresse [http://go.microsoft.com/fwlink/?linkid=268602\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268602%26clcid=0x40c).

## L’installation de Lync Server 2013 échoue sur la version ITA du système d’exploitation Windows Server 2012 RTM (3179467)

**Problème :**

L’installation de Lync Server 2013 échoue sur Windows Server 2012 ITA en raison de l’échec d’installation de Windows Fabric.

L’installation de Windows Fabric échoue car les traces de structure sont créées au format de l’heure HH:MM:SS, alors que dans Windows Server ITA le format de l’heure est HH.MM.SS.

**Solution de contournement :**

Pour contourner ce problème, mettez à jour le Registre système avant d’installer Lync Server 2013. La clé de Registre qui doit être mise à jour est la suivante : HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat. Modifiez la valeur de sTimeFormat to HH:mm:ss à l’aide de interface de ligne de commande Windows PowerShell en procédant comme suit :

1.  Démarrez Windows PowerShell et exécutez les applets de commande suivantes :
    
    ```
    New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
    ```
    ```
    $a="HKU:\.Default\Control Panel\International"
    ```

2.  Pour afficher la valeur actuelle, exécutez l’applet de commande suivante :
    
        Get-itemproperty $a -Name sTimeFormat
    
    Prenez note de la valeur actuelle de sTimeFormat afin de pouvoir la restaurer une fois l’installation terminée.

3.  Pour définir la nouvelle valeur, exécutez l’applet de commande suivante :
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Une fois Lync Server 2013 correctement installé, restaurez la valeur d’origine de sTimeFormat en exécutant l’applet de commande suivante :
    
        - Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3. above>"

## Mobilité

## Problèmes affectant les clients mobiles dans le cadre du processus de basculement d’un serveur (3345992)

**Problème :**

Suite à l’échec d’un serveur Lync Server et au démarrage du processus de basculement, les problèmes suivants peuvent affecter les utilisateurs de clients mobiles :

  - aucun signal ou appel Lync entrant pendant 10 minutes au maximum après le début du basculement ;

  - impossibilité d’accepter les demandes de conversation entrantes ;

  - impossibilité de participer aux réunions si le serveur en échec est le serveur central pour l’utilisateur.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème. Le fonctionnement normal est restauré une fois le processus de basculement terminé.

## Si un utilisateur mobile refuse un appel entrant d’un autre point de terminaison Lync, l’appel est affiché comme conversation manquée sur les clients Lync Mobile (3346251)

**Problème :**

Si un utilisateur mobile refuse un appel entrant provenant d’un autre point de terminaison Lync, l’appel est affiché comme conversation manquée dans le client Lync Mobile, plutôt que sous la forme d’un appel dans la liste des appels de l’appareil.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème.

## Le client mobile n’affiche pas le nom complet d’un contact fédéré lors de la recherche de contacts (3346256)

**Problème :**

Il est possible que le nom complet des contacts fédérés ne s’affiche pas dans le cadre de certains scénarios, tels que la recherche d’un contact fédéré dans la liste des contacts. Cela peut se produire si aucun abonnement aux informations de présence n’est actif pour le contact dans le client Lync Mobile.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème.

## Dans le client mobile, l’invité et les informations d’horodatage ne s’affichent pas dans une conversation manquée correspondant à une invitation à une conférence (3346265)

**Problème :**

Dans le client mobile, si une conversation manquée correspond à une invitation à une conférence, l’invité et les informations d’horodatage ne s’affichent pas dans le message de conversation manquée.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème.

## Les utilisateurs de clients mobiles qui passent des appels via le protocole VoIP ne peuvent pas laisser de message vocal aux utilisateurs dont la messagerie vocale est configurée dans Exchange 2010 ou une version antérieure (3346260)

**Problème :**

Si un utilisateur de client mobile utilise la protocole VoIP pour passer des appels, il ne peut pas laisser de message vocal aux utilisateurs configurés pour utiliser la messagerie vocale dans Microsoft Exchange Server 2007 ou Microsoft Exchange Server 2010.

**Solution de contournement :**

Pour contourner ce problème, utilisez Exchange 2010 avec SP1 ou une version supérieure de Microsoft Exchange Server.

## Lorsque l’option Bloquer avec une URL est utilisée pour la configuration de la version du client sur les clients mobiles, un message d’erreur incorrect peut être affiché (3346258)

**Problème :**

Lorsque l’option **Bloquer avec une URL** est utilisée pour la configuration de la version du client sur les clients mobiles, un message d’erreur incorrect peut être affiché si la version du client n’est pas prise en charge.

**Solution de contournement :**

Pour contourner ce problème, définissez la configuration de la version du client de façon à utiliser l’option **Bloquer** plutôt que l’option **Bloquer avec une URL**.

## Conférence

## Les logiciels antivirus exécutés sur les serveurs frontauxLync Server 2013 peuvent provoquer le recyclage du domaine d’application, qui interrompt momentanément le service pour les clients Lync Web App 2013, Lync Mobile 2010 et Lync Mobile 2013 (3212531)

**Problème :**

Les logiciels antivirus peuvent déclencher des redémarrages du domaine d’application, ce qui peut entraîner la perte d’état des applications clientes d’API web de communications unifiées et Lync Mobility Service 2013 ( Lync Web App 2013, Lync Mobile 2010 et Lync Mobile 2013).

**Solution de contournement :**

Pour contourner ce problème, excluez les dossiers suivants contenant des composants web et le .NET Framework de l’analyse antivirus. Pour plus d’informations, reportez-vous à l’article 312592 de la Base de connaissances Microsoft, intitulé « PRB : redémarrages d’applications aléatoires avec l’erreur « L’application redémarre » dans ASP.NET », à l’adresse [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x40c).

Les dossiers suivants doivent être exclus :

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int

  - %ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext

  - %Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config

## La prise en charge XMLHTTP native ou les contrôles ActiveX doivent être activés dans Windows Internet Explorer pour prendre part à des conférences (2798163)

**Problème :**

Si un utilisateur a désactivé la prise en charge XMLHTTP native et les contrôles ActiveX dans les paramètres du navigateur Internet Windows Internet Explorer, il ne pourra pas prendre part à une réunion si Internet Explorer est sélectionné comme navigateur par défaut.

**Solution de contournement :**

Activez les contrôles ActiveX ou la prise en charge XMLHTTP native dans Internet Explorer.

## Le service de conférence web de Lync Server ne peut pas récupérer du mode critique (2788663)

**Problème :**

Si le mode critique est activé pour l’archivage, en cas de défaillance du système, le mode critique démarre et les conférences ne fonctionnent plus pour les participants. Une fois que l’administrateur a éliminé cette défaillance (par exemple, en résolvant un problème de base de données), le service de conférence de données ne récupère pas automatiquement et l’administrateur doit redémarrer manuellement le service de conférence pour que la conférence reprenne.

**Solution de contournement :**

Un administrateur redémarrer manuellement le service de conférence une fois la défaillance système éliminée.

## Le service de conférence web ignore le proxy HTTP pour les serveurs Office Web App externes (2602182)

**Problème :**

Si vous avez déployé un serveur Office Web Apps Server externe au service de conférence web (à savoir, un serveur qui ne se trouve pas sur le réseau d’entreprise interne) sur le réseau de périmètre Internet et que le service de conférence web requiert un proxy HTTP pour s’y connecter, la découverte Office Web Apps Server échoue. Le service de conférence web ignore le paramètre de proxy HTTP, tel que défini dans le Générateur de topologie du programme d’installation d’Office Web Apps Server. En conséquence, le client Lync ne peut pas bénéficier du partage Microsoft PowerPoint 2010 avec d’autres participants à la conférence. Si vous installez Lync Server localement et configurez également Office Web Apps Server localement sur le réseau interne, aucune configuration de proxy n’est nécessaire.

**Solution de contournement :**

La seule solution de contournement consiste à ne pas avoir de configuration de déploiement qui requiert l’utilisation d’un proxy HTTP pour communiquer avec un serveur Office Web Apps Server externe.

## L’ajout de vidéo à une conférence de fournisseur de services d’audioconférence n’est pas pris en charge (2603861)

**Problème :**

L’ajout de vidéo n’est pas pris en charge si l’utilisateur participe à une conférence de fournisseur de services d’audioconférence pour l’audio.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème.

## Les topologies dans lesquelles le protocole IPv6 est activé forcent la mise à jour automatique du plug-in Silverlight de Lync Web App afin de s’assurer que la fonctionnalité de partage d’écran peut fonctionner à partir de Lync Web App (2604634)

**Problème :**

Lorsqu’une topologie est configurée avec le protocole IPv6 activé, les utilisateurs ne peuvent pas partager leur écran à partir du client Lync Web App si une version antérieure du plug-in de partage d’écran est déjà installée.

**Solution de contournement :**

Pour forcer une mise à jour vers la version la plus récente du plug-in de partage d’écran lors de la participation à une réunion via Lync Web App, modifiez la valeur de **MinSupportedBuildVersion** de « 4.0.7457.0  en « 4.0.7577.380 » dans les deux fichiers suivants :

  - %ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml

  - %ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml

## Voix Entreprise

## Dans certains cas, il est possible qu’un client Lync exécuté sur un ordinateur configuré pour utiliser la double pile IPv4 et IPv6 ne prenne pas en charge les fonctionnalités qui utilisent le sous-réseau IP de l’ordinateur (appels d’urgence, déviation du trafic multimédia, contrôle d’admission des appels et routage géodépendant) (3335508)

> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.

**Problème :**

Lorsqu’un client Lync est exécuté sur un ordinateur activé pour la double pile IPv4 et IPv6 et basé sur la résolution DNS du serveur proxy, il peut utiliser l’adresse IPv6 de l’ordinateur pour se connecter. Dès lors, le client Lync ne prend en charge que les fonctionnalités prises en charge pour IPv6, ce qui exclut les appels d’urgence, la déviation du trafic multimédia, le contrôle d’admission des appels et le routage géodépendant.

**Solution de contournement :**

Pour contourner ce problème, désactivez la prise en charge d’IPv6 sur l’ordinateur client :

## Si Voix Entreprise n’est pas configuré pour un utilisateur, celui-ci doit utiliser le format E164 pour effectuer un appel sortant depuis une conférence (3215342)

**Problème :**

Si Voix Entreprise n’est pas configuré pour un utilisateur, celui-ci doit utiliser le format E164 pour effectuer un appel sortant depuis une conférence. S’il n’utilise pas le format E164, l’utilisateur ne pourra pas effectuer d’appel sortant depuis la conférence.

**Solution de contournement :**

Pour contourner ce problème, les utilisateurs qui ne sont pas activés pour Voix Entreprise doivent effectuer des appels sortants depuis une conférence au moyen de numéros au format E164.

## Présence

## Si un utilisateur a sélectionné l’option « Bloquer toutes les invitations et communications » alors que le magasin de contacts unifié est activé pour cet utilisateur, le statut de présence n’est pas rejeté quand il devrait l’être (3204526)

**Problème :**

Si un utilisateur a sélectionné l’option « Bloquer toutes les invitations et communications » alors que le magasin de contacts unifié est activé pour cet utilisateur, le statut de présence n’est pas rejeté quand il devrait l’être.

**Solution de contournement :**

Pour contourner ce problème, vous pouvez désactiver le magasin de contacts unifié pour l’utilisateur. Pour cela, exécutez les applets de commande suivantes :

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Exemple :

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

## Les utilisateurs d’Office Communications Server 2007 R2 hébergés localement ne peuvent pas voir le statut de présence des utilisateurs de Skype Entreprise Online dans les déploiements hybrides (3014624) - Hybride

**Problème :**

Ce problème peut se produire dans un déploiement hybride quand vous utilisez un directeur Lync Server 2013.

Le statut de présence des utilisateurs hébergés sur Skype Entreprise Online est affiché comme « Présence inconnue » pour les utilisateurs locaux. De plus, les utilisateurs hébergés sur Skype Entreprise Online ne peuvent pas voir le statut de présence des utilisateurs locaux Office Communications Server R2.

**Solution de contournement :**

Pour contourner partiellement ce problème, modifiez le serveur central (msrtcsip-presencehomeserver) des utilisateurs de Skype Entreprise Online de sorte qu’il pointe vers un pool local Lync Server 2013 plutôt que vers le directeur Lync Server 2013. Vous pouvez modifier ce paramètre sur le serveur frontal local.

Cette solution de contournement permet aux utilisateurs de Skype Entreprise Online d’afficher correctement le statut de présence des utilisateurs hébergés sur Office Communications Server 2007 R2.

## application Response Group, application de parcage d’appel et prise d’appel de groupe

## Un appelant peut entendre une seconde d’attente musicale pendant l’établissement d’un appel avec le destinataire (3334097)

> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.

**Problème :**

Lorsqu’un appel est récupéré via la prise d’appel de groupe, l’appelant peut entendre une seconde d’attente musicale pendant l’établissement de l’appel avec le destinataire.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème.

## Un agent Response Group peut se connecter et se déconnecter par le biais d’une console d’agent Lync Server 2010 uniquement auprès de groupes d’agents formels Lync Server 2010 (2773455)

**Problème :**

Un agent Response GroupLync Server 2013 peut se connecter et se déconnecter par le biais d’une console d’agent Lync Server 2010 uniquement auprès de groupes d’agents formels Lync Server 2010. Dans la console d’agent Lync Server 2010, les utilisateurs ne peuvent voir que le Response GroupLync Server 2010 auquel ils appartiennent. Ils ne peuvent voir aucun des Response Groups Lync Server 2013 auxquels ils appartiennent.

**Solution de contournement :**

Si l’agent Response Group est un utilisateur de Lync Server 2013 et qu’il fait partie d’un groupe d’agents formel Lync Server 2013, l’utilisateur doit accéder à la console d’agent Lync Server 2013 directement via une liaison web dans un navigateur pour se connecter et se déconnecter de groupes d’agents Lync Server 2013.

## Un agent Response GroupLync Server 2010 ne peut pas placer d’appels de la part d’un Response GroupLync Server 2013 (2773471)

**Problème :**

Un utilisateur de Lync Server 2010 qui est un agent d’un Response GroupLync Server 2013 ne peut pas effectuer d’appel de la part du Response Group. Le Response GroupLync Server 2013 ne sera pas disponible dans le client Lync pour effectuer un appel.

**Solution de contournement :**

Pour contourner ce problème, vous devez déplacer l’utilisateur de Lync Server 2010 vers Lync Server 2013.

## La suppression d’un Response Group de Lync Server 2010 après sa migration vers Lync Server 2013 empêchera le Response Group d’accepter des appels entrants (3016227)

**Problème :**

Si un Response Group ayant subi une migration de Lync Server 2010 vers Lync Server 2013 est supprimé de Lync Server 2010 par le biais du Panneau de configuration Lync Server ou de Lync Server Management Shell, le Response Group dans Lync Server 2013 cesse de recevoir des appels entrants.

**Solution de contournement :**

Pour contourner ce problème, ne supprimez de Response Groups de Lync Server 2010 ayant subi une migration de Lync Server 2010 vers Lync Server 2013.

Si le Response Group a déjà été supprimé, vous devez le redéployer dans Lync Server 2013.

## Lorsqu’un nouveau flux de travail géré est défini comme inactif lors de sa création, son déploiement échoue (3207527)

**Problème :**

Lorsqu’un nouveau flux de travail géré est défini comme inactif lors de sa création, son déploiement échoue. Ce problème se produit quand le flux de travail est défini comme inactif au moment de sa création, mais il n’affecte pas un flux de travail modifié et défini comme inactif après son déploiement.

**Solution de contournement :**

Lors de la création et du déploiement d’un flux de travail, définissez le flux de travail comme actif, puis déployez-le. Une fois le déploiement réussi, vous pouvez modifier le flux de travail et le définir comme inactif.

## La suppression d’un Response Group du pool propriétaire empêche le Response Group du pool de sauvegarde d’accepter des appels entrants durant le basculement si le Response Group a été importé dans le pool de sauvegarde (3016214)

**Problème :**

Si un Response Group détenu par le pool principal a été importé dans le pool de sauvegarde sans remplacer le propriétaire et que le Response Group est supprimé du pool propriétaire, le Response Group dans le pool de sauvegarde n’accepte aucun appel entrant durant le basculement.

**Solution de contournement :**

Vous devez redéployer le Response Group dans le pool principal, puis exporter la configuration du Response Group à partir du pool principal et la réimporter dans le pool de sauvegarde.

Vous pouvez également recréer le Response Group dans le pool de sauvegarde. Dans ce cas, celui-ci sera le pool propriétaire du Response Group.

## Un appel parqué ne peut pas être récupéré à partir de l’application de parcage d’appel si la demande de récupération est effectuée de la part d’un Response Group (3211798)

**Problème :**

Lorsque les conditions suivantes sont remplies, une demande de récupération pour un appel parqué échoue :

  - Un agent fait partie d’un Response Group anonyme

  - L’agent tente de récupérer un appel parqué à partir de l’application de parcage d’appel par le biais du Response Group anonyme

  - L’agent tente de récupérer l’appel en composant le numéro d’orbite par le biais de l’option Appeler de la part de ou par le biais de la même option dans le client intendant Lync.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème. L’appel parqué doit être récupéré sans que ce soit de la part d’un Response Group.

## Panneau de configuration Lync Server, Générateur de topologie et Outil de planification

## Limitations de l’outil de planification (3331056 et 3331059)

> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.

**Problème :**

L’outil de planification présente les limitations suivantes dans le cadre de la planification de votre déploiement :

  - Jusqu’à 10 sites centraux peuvent être pris en charge

  - Chaque site central peut avoir 14 sites de succursale au maximum

  - Chaque site central peut accueillir jusqu’à 240 000 utilisateurs

Par ailleurs, l’outil de planification n’inclut pas de valeurs pour les éléments suivants dans le cadre du calcul de la topologie recommandée :

  - nombre d’utilisateurs hébergés en ligne ;

  - pourcentage d’utilisateurs activés pour la fédération XMPP ;

  - pourcentage d’utilisateurs utilisant Lync Web App.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ces problèmes. Pour plus d’informations sur l’outil de planification, reportez-vous à [Conception de la topologie pour Lync Server 2013 via l’outil de planification](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

## Il est possible que l’outil de planification ne puisse pas utiliser les adresses IP précédemment définies pour le réseau Edge lors de la mise à jour des options

**Problème :**

Une fois que vous avez finalisé votre conception à l’aide de l’outil de planification, si vous apportez des modifications aux options du réseau Edge, des adresses IP peuvent être ajoutées à la conception, au lieu que les adresses IP existantes ne soient mises à jour. Cela peut se produire lorsque vous affichez les détails du diagramme de réseau Edge, sélectionnez **Cliquez ici pour mettre à jour vos options** , puis, dans la boîte de dialogue Options de configuration, sélectionnez Réseau Edge, puis **Je veux utiliser les mêmes noms de domaine complets (FQDN) et adresses IP, mais des ports différents pour les services Edge sur mon serveur Edge** . L’application de modifications peut entraîner l’ajout de nouvelles adresses IP et de nouveaux serveurs Edge à la conception.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ce problème pour le moment.

## Dans Panneau de configuration Lync Server, « Déplacer tous les utilisateurs vers le pool » peut ne pas fonctionner comme prévu (3199270)

**Problème :**

Lors de l’utilisation du Panneau de configuration Lync Server pour déplacer tous les utilisateurs d’un pool vers un autre dans un environnement Active Directory complexe, par exemple, un environnement avec plusieurs contrôleurs de domaine et domaines parent/enfant, le message d’erreur « L’utilisateur spécifié n’est pas un utilisateur hérité. Utilisez à la place l’applet de commande Move-CsUser » peut être. Cela est dû à l’allongement des durées de réplication dans les environnements Active Directory complexes.

**Solution de contournement :**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Utilisez des filtres dans le Panneau de configuration Lync Server pour rechercher les utilisateurs hérités, sélectionnez ces utilisateurs, puis utilisez la commande **Déplacer les utilisateurs sélectionnés vers le pool** plutôt que **Déplacer tous les utilisateurs vers le pool** .

  - Utilisez Lync Server Management Shell pour déplacer les utilisateurs hérités par lots à l’aide d’applets de commande Lync Server.

## Le Panneau de configuration Lync Server cesse de fonctionner dans un environnement VMware après la mise à jour de plug-in de navigateur Microsoft Silverlight vers la version 5 (3199270)

**Problème :**

Si vous utilisez le Panneau de configuration Lync Server dans un environnement VMware, le Panneau de configuration Lync Server peut cesser de fonctionner après la mise à niveau de Silverlight vers la version 5.

**Solution de contournement :**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Désinstallez Silverlight 5 puis installez Silverlight 4 à partir du site web à l’adresse [http://go.microsoft.com/fwlink/?linkid=149156\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=149156%26clcid=0x40c).

  - Ouvrez le Panneau de configuration Lync Server à partir d’un ordinateur qui n’est pas un ordinateur virtuel VMware.
    
    Pour ouvrir le Panneau de configuration Lync Server à partir d’un ordinateur distant, installez les outils d’administration de Lync Server sur l’ordinateur, puis démarrez le Panneau de configuration Lync Server à partir du menu **Démarrer** de Windows.
    
    Vous pouvez également ouvrir le Panneau de configuration Lync Server en entrant l’URL dans un navigateur web. L’URL sera semblable à https://\<nom\_domaine\_complet\_pool\_frontal\>/cscp.

## Un administrateur ne peut pas exécuter l’applet de commande Uninstall-csMirrorDB après la suppression de la base de données miroir dans le Générateur de topologie (3199266)

**Problème :**

Lorsqu’un administrateur désactive une base de données miroir dans le Générateur de topologie, puis la supprime dans le Générateur de topologie, un message s’affiche dans la Liste des tâches pour signaler à l’administrateur qu’il doit exécuter l’applet de commande **Uninstall-csMirrorDatabase** pour supprimer la mise en miroir de SQL Server. Quand l’administrateur tente d’exécuter l’applet de commande, l’opération échoue.

**Solution de contournement :**

Pour supprimer la mise en miroir SQL d’un pool dans le Générateur de topologie, vous devez d’abord utiliser une applet de commande pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le Générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Par exemple, pour supprimer la mise en miroir et les bases de données pour les bases de données utilisateur, tapez ce qui suit :

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Le paramètre *DropExistingDatabasesOnMirror* permet de supprimer les bases de données affectées du miroir. Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :

1.  Dans le Générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés** .

2.  Désactivez l’option **Activer la mise en miroir du magasin SQL** et cliquez sur **OK** .

3.  Publiez la topologie.

> [!IMPORTANT]  
> Chaque fois que vous apportez une modification à une relation de mise en miroir de bases de données principales, vous devez redémarrer tous les serveurs frontaux du pool.

## Des erreurs de validation sont renvoyées dans le Générateur de topologie quand un administrateur tente de supprimer un déploiement avec un pool frontal associé à un magasin de témoins (3199266)

**Problème :**

Si un administrateur tente d’utiliser la commande **Supprimer le déploiement** dans le Générateur de topologie pour supprimer un déploiement qui comprend un pool frontal associé à un magasin de témoins, une erreur de validation s’affiche dans le Générateur de topologie et l’action n’est pas exécutée.

**Solution de contournement :**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Supprimez le magasin de témoins avant d’essayer de supprimer le déploiement.

  - Ajoutez un magasin de témoins pour le pool frontal, puis supprimez-le.

## Les informations de déploiement du serveur de conversations permanentes sont incohérentes entre l’Outil de planification et le Générateur de topologie (3012228)

**Problème :**

Lorsque l’outil de planification Lync Server 2013 génère le schéma de topologie du site pour un déploiement de serveur de conversations permanentes dans lequel la récupération d’urgence est activée, le schéma de topologie du site inclut plusieurs sites (physiques), avec des serveurs de conversations permanentes affectés de manière égale dans chaque site. Dans le Générateur de topologie, tous les serveurs de conversations permanentes sont représentés comme appartenant à un seul site (logique) et sont répertoriés sous le même nœud de pool de serveurs de conversations permanentes.

**Solution de contournement :**

Il n’existe actuellement aucune solution de contournement à ce problème. L’utilisateur doit analyser la sortie de l’outil de planification pour le déploiement de serveur de conversations permanentes et modifier le plan en fonction de ses propres besoins.

## Localisation

## Analyse

## L’Assistant Déploiement des rapports de surveillance affiche des caractères incorrects dans certaines circonstances lors de l’utilisation de la version d’Asie de l’Est de Lync Server (3113565)

**Problème :**

Lors de l’utilisation d’une version d’Asie de l’Est de Lync Server 2013(par exemple, Chinois (simplifié), Chinois (traditionnel), Japonais ou Coréen) sur un système d’exploitation dont les paramètres régionaux système ne sont pas définis sur une langue de l’Asie de l’Est, l’Assistant Déploiement des rapports de surveillance affiche des points d’interrogation ou d’autres caractères au lieu de messages localisés.

**Solution de contournement :**

Pour résoudre ce problème, définissez les paramètres régionaux du système d’exploitation et de Lync Server 2013 sur la même langue. Tous les messages seront alors affichés correctement.

## Panneau de configuration Lync Server

## Dans certains cas, le premier élément de la barre de navigation supérieure dans une page du Panneau de configuration Lync Server disparaît quand vous cliquez sur le dernier élément de la barre de navigation supérieure.

**Problème :**

Il existe trois cas connus dans lesquels un clic sur le dernier élément de la barre de navigation supérieure dans une page du Panneau de configuration Lync Server provoque la disparition du premier élément de la barre de navigation supérieure :

  - Dans la version française, dans la page « Fédération et accès externe », l’élément « Stratégie d’accès externe » disparaît lorsque vous cliquez sur « Partenaires fédérés XMPP ».

  - Dans la version allemande, dans la page « Clients », l’élément « Clientversionskonfiguration » disparaît lorsque vous cliquez sur « Pushbenachrichtigungskonfiguration ».

  - Dans la version russe, dans la page « Конфигурация сети », l’élément « Глобально » disparaît lorsque vous cliquez sur « Маршрут региона ».

**Solution de contournement :**

Pour contourner ce problème, actualisez la page du Panneau de configuration Lync Server dans votre navigateur. La page sera chargée dans le navigateur avec tous les éléments de la barre de navigation supérieure affichés.

## Carnet d’adresses

## L’indexation dans le carnet d’adresses ne fonctionne pas comme prévu dans certaines langues (3336047)

> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.

Si les propriétés d’un utilisateur incluent un champ indexé contenant uniquement des caractères ne pouvant pas être indexés, l’utilisateur ne s’affiche pas dans les recherches effectuées dans le carnet d’adresses.

Les caractères et paramètres régionaux suivants ne peuvent pas être indexés :

  - Caractères cyrilliques, grecs et arméniens en majuscule

  - Caractères accentués en majuscule

  - Thaï

  - Lao

  - Myanmar

  - Devanâgarî

  - Éthiopien

  - Tibétain

  - Bengali

  - Gujarati

  - Télougou

  - Tous les autres scripts en langues indo-aryennes

## Lync Web App, Web Scheduler et composants web

## La restauration de la langue pour certaines langues dans Lync Web Scheduler, Appel entrant, Lanceur de participation, Gestion des salles de conversation permanente et OCTab peut ne pas fonctionner comme prévu (3079700)

**Problème :**

Lors de la sélection d’un paramètre régional neutre dans un navigateur web (dans Internet Explorer, par exemple, le nom de la langue sans autre spécification, tel que « norvégien \[no\] ») au lieu d’un paramètre régional spécifiant la langue, le script et le paramètre régional (tel que « norvégien (bokmål) (Norvège) \[nb-NO\] ») peut provoquer un comportement d’affichage inattendu pour certaines langues dans Lync Web Scheduler, Appel entrant, Lanceur de participation, Gestion des salles de conversation permanente et OCTab. Par exemple, les utilisateurs peuvent voir la page en anglais lorsque l’une des langues suivantes est sélectionnée :

  - Norvégien

  - Portugais

  - Serbe

**Solution de contournement :**

Si vous souhaitez sélectionner une langue avec un paramètre régional neutre, assurez-vous de toujours ajouter également la langue avec un paramètre régional spécifique (avec script et/ou code de pays) comme langue supplémentaire dans la liste des préférences linguistiques de votre navigateur.

## La prise en charge des paramètres régionaux Azéri et Ouzbek lors de l’utilisation de Lync Web Scheduler, Appel entrant, Lanceur de participation, Gestion des salles de conversation permanente et OCTab est limitée dans certains navigateurs web (3336748)

> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.

**Problème :**

Lorsque vous utilisez Internet Explorer 8 ou Internet Explorer 9, et définissez la langue du navigateur sur Azéri (latin) ou Ouzbek (latin), les pages Appel entrant et Lanceur de participation sont affichées en anglais ou la langue préférée définie dans le navigateur.

Si vous utilisez les navigateurs Firefox ou Chrome, et que vous définissez la langue du navigateur sur Azéri (latin) ou Ouzbek (latin), Lync Web App, Lync Web Scheduler et RGS OCTab sont affichés en anglais ou la langue préférée définie pour le navigateur.

Le paramètre régional Ouzbek (latin) n’est pas pris en charge dans le navigateur Safari.

**Solution de contournement :**

Il n’existe aucune solution de contournement à ces problèmes.

## La flèche déroulante est manquante pour la liste « Rejoindre la réunion » dans la version roumaine de Lync Web App (3154899)

**Problème :**

Lorsqu’un utilisateur de la version roumaine de Lync Web App effectue les étapes suivantes, la flèche déroulante n’est pas affichée pour **Rejoindre la réunion** dans la liste déroulante :

1.  Sélectionnez **Mémoriser mon adresse sur cet ordinateur** sous l’onglet **Général** .

2.  Sélectionnez l’onglet **Téléphone** .

3.  Cliquez sur la liste déroulante pour **Rejoindre la réunion** .
    
    Les utilisateurs ne verront pas de flèche indiquant qu’il existe des options autres que l’option par défaut **Lync Web App**, notamment : **Ne pas établir de connexion audio** (en roumain, « Nu se asociaža la componenta audio ») et **Nouveau numéro** (en roumain, « Numar nou »).

**Solution de contournement :**

Même si la flèche de cette liste déroulante n’est pas affichée, les utilisateurs peuvent tout de même sélectionner les paramètres supplémentaires dans la liste en cliquant sur la valeur par défaut.

## Lors de l’utilisation de la version turque de Lync Web Scheduler, une réunion ne peut pas être enregistrée en cas d’activation de l’option « Personnes que j’ai choisies » sous « Présentateur » (3169483)

**Problème :**

Lors de la création ou de la modification d’une réunion dans la version turque de Lync Web Scheduler, l’option « Personnes que j’ai choisies » sous « Présentateur » n’est pas prise en charge. Lorsque cette option est sélectionnée, la réunion ne peut pas être enregistrée. Au lieu de cela, un message d’erreur s’affiche et indique qu’une ou plusieurs personnes ne peuvent pas être présentateurs.

**Solution de contournement :**

Pour contourner ce problème, les utilisateurs peuvent sélectionner l’option par défaut « Personnes de ma société » ou tout autre choix tel que « Seul l’organisateur » ou « Tout le monde, y compris les personnes extérieures à ma société ». L’organisateur peut rétrograder ou promouvoir les personnes à leur rôle correct ultérieurement, une fois qu’elles ont rejoint la réunion.

En guise d’alternative, les utilisateurs qui comprennent une autre langue peuvent modifier la sélection de langue dans leur navigateur, choisir l’une des 43 langues prises en charge et essayer d’utiliser l’option « Personnes que j’ai choisies ».

## Copyright

Ce document traite d’une version préliminaire d’un produit logiciel qui pourra faire l’objet de modifications substantielles préalablement à la version commerciale finale et constitue des informations confidentielles et appartenant à Microsoft Corporation. Il est divulgué conformément à un accord de confidentialité entre le bénéficiaire et Microsoft. Ce document est fourni uniquement à titre informatif et Microsoft exclut toute garantie, expresse ou implicite, en ce qui concerne ce document. Les informations contenues dans ce document, y compris les URL et autres références à des sites web Internet, pourront faire l’objet de modifications sans préavis. L’utilisateur reconnaît assumer tous les risques liés à l’utilisation de ce document. Sauf mention contraire, les noms de sociétés, d’organisations, de produits, de personnes ou les événements mentionnés dans les exemples sont fictifs. Toute ressemblance avec des noms ou des événements réels est purement fortuite et involontaire. L’utilisateur est tenu d’observer la réglementation relative aux droits d’auteur applicable dans son pays. Aucune partie de ce document ne peut être reproduite, stockée ou introduite dans un système de restitution, ou transmise à quelque fin ou par quelque moyen que ce soit (électronique, mécanique, photocopie, enregistrement ou autre) sans la permission expresse et écrite de Microsoft Corporation.

Microsoft peut détenir des brevets, avoir déposé des demandes d’enregistrement de brevets ou être titulaire de marques, droits d’auteur ou autres droits de propriété intellectuelle portant sur tout ou partie des éléments qui font l’objet du présent document. Sauf stipulation expresse contraire d’un contrat de licence écrit de Microsoft, la fourniture de ce document n’a pas pour effet de vous concéder une licence sur ces brevets, marques, droits d’auteur ou autres droits de propriété intellectuelle.

© 2012 Microsoft Corporation. Tous droits réservés.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook et SQL Server sont soit des marques de Microsoft Corporation, soit des marques déposées de Microsoft Corporation, aux États-Unis et/ou dans d’autres pays/régions.

Toutes les autres marques sont la propriété de leur détenteur respectif.

