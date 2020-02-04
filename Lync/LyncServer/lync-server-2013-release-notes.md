---
title: Notes de publication de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10961f0a8e59fe1d0dc0268b430f37fd294252b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Notes de publication de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-08_

Bienvenue dans les notes de publication de Lync Server 2013. Pour plus d’informations sur les problèmes connus concernant Lync Server 2013, consultez ce fichier.

<div>

## <a name="about-this-document"></a>À propos de ce document

Ce document contient des informations importantes à connaître avant de déployer et d’utiliser Lync Server 2013. Pour plus d’informations sur Lync Server 2013, voir la documentation [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .

Ce document contient les sections suivantes :

  - Client 2013 Lync

  - Lync Server

  - Installation

  - Mobilité

  - Conférence

  - Voix Entreprise

  - Présence

  - Application Response Group et application Parcage d’appel

  - Panneau de configuration Lync Server, générateur de topologie et outil de planification

  - Localisation

  - Reproduction

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Client 2013 Lync

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>Échec du transfert d’un fichier dans un message instantané si le fichier est ouvert dans une autre application

**Émet**

Si vous essayez de transférer un fichier, tel qu’un document Word, en l’incluant dans un message instantané à un autre utilisateur Lync, le transfert semble aboutir, mais il se peut que le transfert du fichier échoue. Une icône pour le type de fichier s’affichera dans le client Lync, mais le fichier ne peut pas être ouvert par le destinataire prévu. Aucun message d’erreur ne s’affiche pour vous signaler que le transfert a échoué.

**Moyens**

Pour contourner ce problème, fermez l’application ou le fichier ouvert qui s’ouvre avant d’essayer de transférer le fichier dans un message instantané.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Si la réplication des données du service de stockage Lync Server échoue, les administrateurs doivent vérifier les compteurs de performance pour les éléments de la file d’attente du service de stockage obsolète

**Émet**

Le service de stockage Lync Server utilise Windows fabric pour la réplication. Si les données sont supprimées sur un serveur frontal principal, mais que la suppression d’un serveur frontal secondaire échoue (par exemple, en cas d’arrêt inattendu ou d’erreur sur le serveur frontal), les données peuvent être laissées au-dessus et « orphelines ». Les données orphelines peuvent entraîner une dégradation des performances et gaspiller l’espace disque.

**Moyens**

Pour contourner ce problème, si les événements LYSS\_DB\_de\_la\_base de données (ID = 32058)\_et\_LYSS\_DB\_utilisés comme Critical (ID = 32059) sont générés dans le journal des événements, les administrateurs doivent vérifier le compteur de performance du serveur frontal sous **ls : LYSS-API du service** de stockage dont le nom est **LYSS**. Si ce compteur de performance a une valeur élevée (par exemple, supérieure à 50 000), l’administrateur doit exécuter l’outil CleanuUpStorageServiceData. exe dans le kit de ressources de Lync Server 2013, qui supprimera toutes les données orphelines du pool. Pour plus d’informations sur l’outil, voir la documentation du kit de ressources de Lync Server 2013.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Chaque fois que la configuration de l’adresse IP d’un serveur ou d’un pool est modifiée, vous devez redémarrer les services Lync Server.

**Émet**

Lorsque la configuration de l’adresse IP d’un déploiement de Lync Server 2013 est modifiée (par exemple, le passage d’une pile IPv4 à une pile double ou d’une pile passant à une pile IPv6), tous les composants serveur ne prennent pas en main la modification de la configuration tant qu’il n’est pas redémarré.

**Moyens**

Pour contourner ce problème, redémarrez les services Lync Server suite à la modification de la configuration d’adresse IP pour le déploiement. Pour cela, exécutez les applets de commande suivantes dans Lync Server Management Shell :

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>L’applet de connexion de transaction synthétique de conférence rendez-vous n’est plus disponible dans le pack d’administration 2013 de Lync Server.

**Émet**

L’applet de **contrôle** de conférence rendez-vous de la Conférence rendez-vous n’est plus disponible dans le pack d’administration 2013 de Lync Server.

**Moyens**

L’utilisation de l’applet de **contrôle** de conférence rendez-vous est prise en charge uniquement en interne pour une entreprise.

Les administrateurs peuvent continuer à utiliser l’applet de cmdlet dans Lync Server Management Shell à des fins de dépannage. Le cas échéant, une entreprise peut également développer un pack d’administration privé pour exécuter l’applet de demande en interne.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>Le service de journalisation centralisé s’arrête si le trafic réseau a été interrompu lors de la copie des fichiers journaux vers le partage réseau.

**Émet**

Lorsque le service de journalisation centralisé est configuré pour utiliser un chemin d’accès réseau (la valeur du paramètre CacheFileNetworkFolder de l’applet de connexion **Get-CsClsConfiguration** est un chemin UNC valide), les fichiers journaux mises en cache sont copiés sur le partage réseau. S’il y a un problème de trafic réseau lors de la copie des fichiers, une exception se produit, ce qui entraîne l’arrêt du service de journalisation centralisé.

Le service est configuré pour un démarrage automatique à trois reprises, de sorte que le service récupère les trois premières exceptions.

**Moyens**

Il n’existe aucune solution de contournement pour ce problème. Pour identifier le problème, analysez le journal des événements pour l’ID d’événement 7031 à partir du « gestionnaire de contrôle de service » qui consigne le service « Lync Server central Logging agent » s’est arrêté de manière inattendue. S’il s’agit de plus de trois fois, redémarrez manuellement le service à l’aide de l’applet de passe **Start-CsWindowService** .

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Les éléments de la file d’attente du service de stockage doivent être importés manuellement

**Émet**

Lync Server 2013 stocke les données relatives aux conférences et à la messagerie instantanée, telles que les messages archivés et l’enregistrement des détails des appels, sur une base de données sur chaque serveur frontal. Les données sont stockées dans la base de données pendant son traitement avant d’être remises à la destination prévue. Pour améliorer les performances, Lync Server 2013 exporte périodiquement les éléments de la file d’attente à partir de la base de données locale qui ne sont pas traités pendant une période prolongée et les enregistre sur le magasin de fichiers. Si le magasin de fichiers n’est pas disponible, les éléments sont stockés sur chaque serveur frontal. La même opération se produit afin d’éviter les pertes de données pendant le basculement du pool.

Pendant l’opération d’exportation, le service de stockage du serveur Lync enregistre chaque étape du journal des événements avec les ID d’événement de 32075 (l’opération de vidage complète est lancée), 32076 (vidage complet est effectué), 32082 (le vidage du niveau de maintenance est démarré), 32083 (vidage de niveau de maintenance est terminé), 32089 (le vidage s’est produit en raison du remplissage de la base de données). Ces données ne seront pas automatiquement importées sur le système pour être traitées et transmises à la destination finale (SQL Server ou Exchange Server).

**Moyens**

Pour importer les données dans le système, les administrateurs doivent utiliser l’outil ImportStorageServiceData dans le kit de ressources de Lync Server, qui ajoute les données dans le système afin qu’elles soient traitées et transmises à la destination finale.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Les recherches dans le carnet d’adresses Web peuvent échouer si la valeur par défaut de UseNormalizationRules est remplacée par false.

**Émet**

Si la valeur par défaut de UseNormalizationRules est remplacée par false, les recherches de requête sur le Web du carnet d’adresses échouent. Après la modification de la valeur par défaut, les utilisateurs du client Lync ne seront pas en mesure d’utiliser la requête Web du carnet d’adresses Lync pour rechercher des utilisateurs.

**Moyens**

Si la valeur par défaut de UseNormalizationRules est définie sur false, afin que les utilisateurs puissent utiliser des numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory sans Lync Server 2013 appliquant des règles de normalisation, contourner ce problème en procédant comme suit :

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Effectuez l’une des actions suivantes :
    
      - Si votre déploiement inclut uniquement les serveurs Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de UseNormalizationRules et IgnoreGenericRules sur true :
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si votre déploiement inclut une combinaison de Lync Server 2013 et de Lync Server 2010 ou Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 dans la topologie :
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendez la fin de la réplication CMS sur tous les pools.

4.  Modifiez le fichier de règles de normalisation du téléphone pour votre déploiement pour effacer le contenu. Le fichier se trouve sur le partage de fichiers de chaque pool Lync Server 2013. Si le fichier n’est pas présent, créez-en un dans la section\_«\_\_règles\_de normalisation des numéros de téléphone de l’entreprise ».

5.  Attendez quelques minutes pour que tous les pools du serveur principal lisent les nouveaux fichiers.

6.  Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 dans votre déploiement.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>Le message d’erreur de serveur du carnet d’adresses 21054 est généré quotidiennement pour chaque pool 2013 de Lync

**Émet**

Le serveur du carnet d’adresses Lync Server 2013 génère un événement d’erreur 21054 une fois tous les jours lors de la maintenance quotidienne. Cette erreur est également générée chaque fois qu’un administrateur exécute l’applet de connexion **Update-csAddressBook** , même si la mise à jour est réussie. Toutefois, l’événement d’erreur peut être ignoré en toute sécurité lorsque la mise à jour est réussie.

**Moyens**

Lorsque vous rencontrez cet événement d’erreur, exécutez l’applet de commande suivante :

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Si l’applet de passe signale qu’il n’y a aucun objet non indexé ou abandonné, l’événement d’erreur 21054 peut être ignoré en toute sécurité.

Par ailleurs, le témoin d’intégrité principal (KHI) « les utilisateurs du carnet d’adresses correctement indexé » doit être désactivé dans System Center Operations Manager.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>Les requêtes peuvent échouer lorsque le protocole IPv6 est configuré sur un pool de bords

**Émet**

Lorsque le protocole IPv6 est configuré sur un pool Edge, certaines requêtes vers le pool Edge peuvent échouer.

**Moyens**

Pour contourner ce problème, ne configurez pas de pool Edge avec IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>L’applet de passe Invoke-csPoolFailback risque de ne pas fonctionner lors du retour automatique de la liste

**Émet**

Lorsque vous tentez de basculer sur un pool, l’applet de demande **Invoke-csPoolFailback** risque d’échouer en raison de l’erreur « Échec de l’accomplissement du processus d’hydratation après plusieurs tentatives ».

**Moyens**

Pour contourner ce problème, exécutez de nouveau l’applet de passe et attendez que l’applet de passe réussisse. Notez que le processus de restauration automatique peut prendre quelques minutes. Un délai de 60 minutes doit être nécessaire pour un pool avec des utilisateurs 20 000.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>Une perte de données est susceptible de se produire lorsque vous ajoutez un serveur frontal à une réserve déjà établie-hybride, Skype entreprise Online

**Émet**

Ce problème peut se produire dans un environnement dans lequel un pool a plusieurs serveurs frontaux et que vous redémarrez l’un des serveurs frontaux ou ajoutez un nouveau serveur frontal qui ne faisait pas partie de la liste.

Les utilisateurs dont les données sont archivées peuvent faire l’objet d’une perte de données jusqu’à ce qu’une distribution stable de l’archivage des données soit établie pour le pool. Ce délai de perte de données potentiel est limité à 15 minutes pour les conversations de personne à personne et de 30 minutes pour les conférences.

**Moyens**

Lorsque vous effectuez une maintenance, au lieu de démarrer les serveurs frontaux dans le groupe, vous devez basculer le pool vers un autre, puis effectuer des tâches de maintenance sur les serveurs. Vous pouvez également rendre le Service indisponible avant d’effectuer des tâches de maintenance, puis restaurer la disponibilité au terme de la maintenance.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Les administrateurs ne peuvent pas obtenir le nombre de licenciés à l’aide de l’applet de passe Get-CsClientAccessLicense

**Émet**

Les administrateurs ne peuvent pas obtenir une utilisation précise des licences client en utilisant l’applet de commande **Get-CsClientAccessLicense** .

**Moyens**

Pour vérifier le type de licence serveur, vous pouvez exécuter l’applet de contrôle **Get-CsService** pour récupérer les noms de domaine complets (FDQNs) de toutes les bases de données. Si le nom de domaine complet du serveur principal est identique à celui de la base de données principale, la licence est une licence Standard Edition. Dans le cas contraire, la licence est une licence Enterprise Edition.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>Le nombre de licenciés du client n’est pas correctement signalé

**Émet**

Lorsque vous déterminez le nombre de licences clientes, vous pouvez observer les conditions suivantes :

1.  **Nombre de licences inexactes pour les utilisateurs mobiles**
    
    Le nombre de licences est basé sur le nombre d’adresses IP uniques pour les utilisateurs de périphériques. Le nombre de licences sera limité des manières suivantes :
    
      - Les licences seront surconsidérées si l’adresse IP de l’utilisateur change au cours des sessions Lync. Cela peut se produire lorsqu’un utilisateur se connecte à Lync Server à partir de plusieurs emplacements auprès d’un client de bureau.
    
      - Les licences seront sous-comptabilisées si un utilisateur se connecte à un client mobile, car l’adresse IP de l’appareil ne peut pas être déterminée.

2.  **Les licences sont comptabilisées à deux reprises pour les appels de réseau téléphonique commuté (PSTN) vers le client Lync, les appels client Lync vers les lignes RTC et les appels Lync renvoyés vers des lignes PSTN**
    
    Dans les scénarios suivants, deux licences supplémentaires seront comptabilisées au lieu d’une telle sorte que le numéro de téléphone et l’utilisateur Lync soient pris en compte pour déterminer le nombre de licences utilisées. Pour obtenir des informations précises sur la gestion des licences, supprimez manuellement les licences générées par un numéro de téléphone.
    
      - Appel téléphonique PSTN vers Lync
    
      - Appel Lync vers une ligne RTC
    
      - Un appel RTC sur Lync, puis Lync transfère l’appel vers une ligne PSTN. Une des lignes RTC sera comptée.

3.  **Une licence ne sera pas comptabilisée pour un téléphone Lync connecté**
    
    Lorsqu’un utilisateur utilise un téléphone certifié Lync, si le téléphone se connecte et reste connecté, ce qui conserve son statut de connexion, le téléphone ne sera pas comptabilisé comme utilisant une licence si la requête de licences intervient après la connexion du téléphone.

4.  **Licences comptabilisées pour les téléphones RTC qui se connectent à des conférences**
    
    Lorsqu’un utilisateur rejoint une conférence à l’aide d’un téléphone RTC, une licence n’est pas correctement comptabilisée pour rejoindre la Conférence. Toutefois, aucune licence n’est nécessaire pour participer à une conférence à l’aide d’un téléphone RTC.

**Moyens**

1.  **Nombre de licences inexactes pour les utilisateurs mobiles**
    
      - Vous pouvez identifier les adresses IP qui appartiennent au même appareil et en supprimer une dans le nombre de licences.
    
      - Il n’existe aucune solution de contournement pour ce problème avec les appareils mobiles qui se connectent avec le client Lync.

2.  **Les licences sont comptabilisées deux fois pour les appels RTC vers le client Lync, les appels client Lync vers les lignes RTC et les appels Lync transférés vers les lignes RTC**
    
    Vous devez identifier manuellement le numéro de téléphone RTC et supprimer le nombre de licences qui lui est généré.

3.  **Une licence ne sera pas comptabilisée pour un téléphone Lync connecté**
    
    Vous pouvez configurer le téléphone Lync pour vous déconnecter, puis vous reconnecter à un intervalle régulier, par exemple tous les 3 mois.

4.  **Licences comptabilisées pour les téléphones RTC qui se connectent à des conférences**
    
    Vous pouvez identifier manuellement le numéro de téléphone RTC qui est utilisé pour participer à la Conférence et supprimer la licence générée par le numéro de téléphone.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Le panneau de configuration de Lync Server cesse de fonctionner dans un environnement VMware après la mise à niveau vers Silverlight 5

**Émet**

Si vous utilisez le panneau de configuration de Lync Server dans un environnement VMware, il est possible que le panneau de configuration de Lync Server cesse de fonctionner après la mise à niveau de Microsoft Silverlight vers la version 5.

**Moyens**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Désinstaller Silverlight 5, puis installer Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)à partir de.

  - Accédez au panneau de configuration de Lync Server à partir d’un ordinateur qui n’est pas un ordinateur virtuel VMware.
    
    Pour ce faire, vous pouvez démarrer le panneau de configuration de Lync Server à partir du menu **Démarrer** de Windows sur le serveur, si les outils d’administration de Lync Server sont installés sur votre ordinateur.
    
    Vous pouvez également accéder au panneau de configuration de Lync Server à l’aide d’un navigateur Web. L’URL sera similaire à celle du\<nom\_de\_domaine\>complet du pool https:///CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>Les informations utilisateur du service de carnet d’adresses ne sont pas mises à jour lorsque le nom complet de l’utilisateur est modifié dans Active Directory

**Émet**

Si le nom distinctif d’un utilisateur (également appelé DN) est modifié dans les services de domaine Active Directory (AD DS), les modifications supplémentaires ne seront pas mises à jour dans le service de carnet d’adresses (ABS). Cela n’affecte pas la connexion ou la présence de l’utilisateur, mais empêche la communication de l’utilisateur si l’adresse SIP est également modifiée, car la recherche renverra une adresse SIP obsolète.

**Moyens**

Pour contourner ce problème, ne modifiez pas le nom d’utilisateur de l’utilisateur. Si vous rétablissez la valeur précédente pour l’utilisateur, les mises à jour sont reflétées dans le service de carnet d’adresses.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Installation

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>L’utilisation de caractères non ASCII risque de provoquer un échec du démarrage de Lync Server.

**Émet**

Le programme d’installation ne fonctionnera pas si le nom du dossier de destination inclut des caractères non ASCII (par exemple, UNICODE, jeu de caractères codés sur deux octets (DBCS), UTF-8 et UTF-16). De plus, le programme d’installation peut réussir, mais le serveur ne démarrera pas si des caractères non-ASCII sont contenus dans les éléments suivants :

  - Nom de l’ordinateur

  - Nom du domaine

  - Nom d'utilisateur

  - URI SIP de l’utilisateur

  - Nom du compte de service

**Moyens**

Utilisez uniquement des caractères ASCII dans le nom du dossier de destination, le nom de l’ordinateur, le nom de domaine, le nom d’utilisateur, l’URI SIP de l’utilisateur et les noms de compte de service.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>Le correctif pour la corruption du tas se produit lorsqu’un module appelle la méthode InsertEntityBody dans IIS 7,5» doit être installé avant d’installer Lync Server 2013

**Émet**

Le correctif pour la corruption du tas se produit lorsqu’un module appelle la méthode InsertEntityBody dans IIS 7,5[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)"(), décrite dans l’article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)) de la base de connaissances Microsoft, doit être installé avant d’installer Lync Server 2013.

**Moyens**

Téléchargez et installez le correctif à partir du centre de téléchargement [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)Microsoft à l’adresse.

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 ne peut pas être installé sur la version du système d’exploitation Windows Server 2012 du système d’exploitation ITA

**Émet**

Échec de l’installation de Lync Server 2013 sur le Windows Server 2012 en raison de l’échec de l’installation de Windows fabric.

Échec de l’installation de Windows fabric, car les traces de fabrique sont créées au format HH : MM : SS. Toutefois, dans le Windows Server ITA, le format horaire est HH. MM.SS.

**Moyens**

Pour contourner ce problème, mettez à jour le registre système avant d’installer Lync Server 2013. La clé de Registre qui doit être mise à jour est\_:\\utilisateurs de HKEY. Panneau\\\\de configuration par\\défaut sTimeFormat international. Définissez la valeur de sTimeFormat sur HH : mm : SS en utilisant l’interface de ligne de commande Windows PowerShell comme suit :

1.  Démarrez Windows PowerShell et exécutez les applets de commande suivantes :
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Pour afficher la valeur actuelle, exécutez l’applet de commande suivante :
    
        Get-itemproperty $a -Name sTimeFormat
    
    Notez la valeur actuelle de sTimeFormat afin qu’elle puisse être restaurée une fois l’installation terminée.

3.  Pour définir une nouvelle valeur, exécutez l’applet de commande suivante :
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Après l’installation de Lync Server 2013, restaurez la valeur d’origine pour sTimeFormat en exécutant l’applet de commande suivante :
    
        - Set-ItemProperty $a-name sTimeFormat-value» <valeur notée à l’étape 3. au-dessus de> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Mobilité

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Problèmes pour les clients mobiles au cours du processus de basculement du serveur

**Émet**

En cas d’échec du serveur Lync et du démarrage du processus de basculement, les problèmes suivants peuvent affecter les utilisateurs des clients mobiles :

  - Aucun appel ou signal entrant Lync n’est effectué pendant 10 minutes après le démarrage du basculement.

  - Impossible d’accepter les demandes de conversation entrantes

  - Impossible de rejoindre des réunions si le serveur en panne est le serveur de base pour l’utilisateur

**Moyens**

Il n’existe aucune solution de contournement pour ce problème. Les fonctionnalités normales seront restaurées une fois le processus de basculement terminé.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Si un utilisateur mobile décline un appel entrant d’un autre point de terminaison Lync, l’appel est affiché en tant que conversion manquée sur les clients mobiles Lync

**Émet**

Si un utilisateur mobile décline un appel entrant et que l’appel provient d’un autre point de terminaison Lync, l’appel s’affiche sous la forme d’une conversation manquée dans le client mobile Lync au lieu d’un appel dans la liste d’appels d’appareil.

**Moyens**

Il n’existe aucune solution de contournement pour ce problème.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>Le client mobile ne peut pas afficher le nom complet d’un contact fédéré lors de la recherche de contacts

**Émet**

Dans certains cas, le nom d’affichage des contacts fédérés ne s’affiche pas, par exemple lors de la recherche d’un contact fédéré dans la liste de contacts. Cela peut se produire lorsqu’il n’y a aucun abonnement de présence actif pour le contact à partir du client mobile Lync.

**Moyens**

Il n’existe aucune solution de contournement pour ce problème.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>Dans le client mobile, les informations d’invité et d’horodatage sont manquantes dans une conversation manquée qui est une invitation à une conférence

**Émet**

Dans le client mobile, lorsqu’une conversation manquée est une invitation à une conférence, les informations invité et horodatage sont manquantes dans le message de conversation manqué.

**Moyens**

Il n’existe aucune solution de contournement pour ce problème.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Les utilisateurs des clients mobiles effectuant des appels à l’aide de VoIP ne peuvent pas quitter la messagerie vocale pour les utilisateurs dont la messagerie vocale est configurée dans Exchange 2010 ou les versions précédentes.

**Émet**

Si un utilisateur du client mobile utilise le protocole VoIP pour passer des appels, l’utilisateur ne pourra pas quitter les messages vocaux pour les utilisateurs configurés pour utiliser la messagerie vocale dans Microsoft Exchange Server 2007 ou Microsoft Exchange Server 2010.

**Moyens**

Pour contourner ce problème, utilisez Exchange 2010 avec SP1 ou une version plus récente de Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Lors de l’utilisation de l’application bloc with URL pour la configuration de la version client sur des clients mobiles, un message d’erreur s’affiche

**Émet**

Lors de l’utilisation de l’application **bloc with URL** pour la configuration de la version client sur des clients mobiles, un message d’erreur incorrect peut s’afficher lorsque la version du client n’est pas prise en charge.

**Moyens**

Pour contourner ce problème, configurez la configuration de version de client de façon à ce qu’elle utilise **bloc** au lieu de **bloquer avec une URL**.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Conférence

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Un logiciel antivirus exécuté sur des serveurs frontaux Lync Server 2013 peut entraîner le recyclage du domaine d’application, ce qui interrompt temporairement le service pour Lync Web App 2013, Lync Mobile 2010 et les clients Lync mobile 2013.

**Émet**

Un logiciel antivirus peut déclencher les redémarrages de domaine d’application, ce qui peut entraîner l’exécution d’applications clientes d’API de mobilité Lync 2013 et de communications unifiées (UC) sur les applications clientes (Lync Web App 2013, Lync Mobile 2010 et Lync mobile 2013).

**Moyens**

Pour contourner ce problème, excluez les dossiers contenant des composants Web et .NET Framework de l’analyse antivirus. Pour plus d’informations, reportez-vous à l’article 312592 de la base de connaissances Microsoft « problème : les redémarrages de l’application aléatoire avec [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)«l’application redémarre » dans ASP.net».

Les dossiers suivants doivent être exclus :

  - % ProgramFiles%\\Microsoft Lync Server 2013\\composants Web\\Components MCX\\ext

  - % ProgramFiles%\\Microsoft Lync Server 2013\\composants Web\\Components MCX\\ent

  - % ProgramFiles%\\Microsoft Lync Server 2013\\composants Web\\Components Ucwa\\ent

  - % ProgramFiles%\\Microsoft Lync Server 2013\\composants Web\\Components Ucwa\\ext

  - % Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>Les contrôles ActiveX ou la prise en charge native de XMLHTTP doivent être activés dans Windows Internet Explorer pour pouvoir participer à des conférences

**Émet**

Si un utilisateur a désactivé les contrôles ActiveX et la prise en charge du programme XMLHTTP natif dans Windows Internet Explorer, l’utilisateur ne pourra pas participer à une réunion si Internet Explorer est sélectionné comme navigateur par défaut.

**Moyens**

Activez les contrôles ActiveX ou le « support XMLHTTP natif » dans Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Le service de conférence Web de Lync Server ne peut pas être récupéré à partir du mode critique

**Émet**

Si le mode critique est activé pour l’archivage, en cas de pannes système, le mode Critical démarre et les conférences ne fonctionneront plus pour les participants. Une fois que l’administrateur a résolu les défaillances du système (par exemple, correction d’un problème de base de données), le service de conférence de données ne se restaure pas automatiquement, et l’administrateur doit redémarrer manuellement le service de conférence pour qu’il reprenne.

**Moyens**

Une fois le système résolu, un administrateur doit redémarrer manuellement le service de conférence.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Le service de conférence Web ignore le proxy HTTP pour les serveurs Office Web App externes

**Émet**

Si vous avez déployé un serveur Office Web Apps externe au service de conférence Web (autrement dit, un serveur qui n’est pas présent dans le réseau d’entreprise interne) sur Internet, le réseau de périmètre et le service de conférence Web nécessite un proxy HTTP pour se connecter à cette application, le La découverte d’Office Web Apps Server échoue. Le service de conférence Web ignore le paramètre proxy HTTP, tel qu’il est défini dans générateur de topologie pour l’installation d’Office Web Apps Server. Par conséquent, le client Lync ne sera pas en mesure d’effectuer le partage de 2010 Microsoft PowerPoint avec les autres participants à la Conférence. Si vous installez Lync Server en local et configurez également Office Web Apps Server en local sur le réseau interne, une configuration de proxy n’est pas requise.

**Moyens**

La seule solution de contournement consiste à ne pas avoir de configuration de déploiement qui nécessite l’utilisation du proxy HTTP pour communiquer avec un serveur Office Web Apps externe.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>L’ajout de la vidéo à une conférence du fournisseur de services d’audioconférence n’est pas pris en charge

**Émet**

L’ajout d’une vidéo n’est pas pris en charge si l’utilisateur est joint à une conférence de fournisseur de services d’audioconférence pour le son.

**Moyens**

Il n’existe aucune solution de contournement pour ce problème.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Les topologies avec IPv6 activé forcent la mise à jour automatique du plug-in Lync Web App pour garantir le fonctionnement du partage d’écran à partir de Lync Web App

**Émet**

Lorsqu’une topologie est configurée avec l’option IPv6 activée, les utilisateurs ne peuvent pas partager leur écran à partir du client Lync Web App si une version antérieure du plug-in de partage d’écran est déjà installée.

**Moyens**

Pour forcer une mise à jour vers la version la plus récente du plug-in de partage d’écran lors de la participation à une réunion via Lync Web App, remplacez la valeur de **MinSupportedBuildVersion** par « 4.0.7457.0 » par « 4.0.7577.380 » dans les deux fichiers suivants :

  - % ProgramFiles%\\Microsoft Lync Server 15\\composants\\Web ont\\atteint\\les\\plug\\-ins de clients ReachAppShPluginProperties. Xml

  - % ProgramFiles%\\Microsoft Lync Server 15\\composants\\Web sont\\accessibles\\à\\l'\\extension du client ReachAppShPluginProperties. Xml

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Voix Entreprise

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>Dans certains cas, un client Lync exécuté sur un ordinateur configuré pour utiliser la pile double IPv4 et IPv6 peut ne pas prendre en charge les fonctionnalités qui dépendent du sous-réseau IP de l’ordinateur (par exemple, E911, dérivation multimédia, contrôle d’admission des appels et routage basé sur l’emplacement).

<div class="">


> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

**Émet**

Lorsqu’un client Lync est en cours d’exécution sur un ordinateur activé pour la pile IPv4 et IPv6 et en fonction de la résolution DNS du serveur proxy, le client peut utiliser l’adresse IPv6 de l’ordinateur pour se connecter. Après cela, le client Lync ne prend en charge que les fonctionnalités prises en charge pour IPv6, ce qui exclut E911, le contournement du média, le contrôle d’admission des appels et le routage basé sur l’emplacement.

**Moyens**

Pour contourner ce problème, désactivez la prise en charge du protocole IPv6 sur l’ordinateur client.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Si voix entreprise n’est pas configurée pour un utilisateur, l’utilisateur doit utiliser le format E164 pour appeler à partir d’une conférence

**Émet**

Si voix entreprise n’est pas configurée pour un utilisateur, il doit utiliser le format E164 pour qu’il se connecte correctement à partir d’une conférence. Si le format E164 n’est pas utilisé, l’utilisateur ne pourra pas se connecter à partir de la Conférence.

**Moyens**

Pour contourner ce problème, les utilisateurs qui ne sont pas activés pour voix entreprise doivent composer d’une conférence en utilisant des numéros au format E164.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Présence

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Si un utilisateur a sélectionné « bloquer toutes les invitations et communications » alors que le magasin de contacts unifié est activé pour l’utilisateur, le statut de présence n’est pas rejeté s’il devrait être

**Émet**

Si un utilisateur a sélectionné « bloquer toutes les invitations et communications » alors que le magasin de contacts unifié est activé pour l’utilisateur, le statut de présence n’est pas rejeté le cas échéant.

**Moyens**

Pour contourner ce problème, vous pouvez désactiver le magasin de contacts unifié pour l’utilisateur. Pour cela, exécutez les applets de commande suivantes :

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Par exemple :

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Les utilisateurs d’Office Communications Server 2007 R2 hébergés sur site ne peuvent pas voir le statut de présence des utilisateurs Skype entreprise Online dans des déploiements hybrides-hybrides

**Émet**

Le problème est susceptible de se produire dans un déploiement hybride lorsque vous utilisez un directeur 2013 de Lync Server.

Le statut de présence des utilisateurs hébergés dans Skype entreprise Online est affiché en tant que présence inconnue pour les utilisateurs locaux. De plus, les utilisateurs hébergés sur Skype entreprise Online ne peuvent pas voir le statut de présence des utilisateurs Office Communications Server R2 locaux.

**Moyens**

Pour contourner ce problème, vous devez modifier le serveur principal (msRTCSIP-presencehomeserver) des utilisateurs de Skype entreprise Online pour qu’ils pointent vers un pool Lync Server 2013 local au lieu du Director Lync Server 2013. Vous pouvez modifier ce paramètre sur le serveur frontal local.

Cette solution de contournement affiche correctement le statut de présence des utilisateurs hébergés sur Office Communications Server 2007 R2 aux utilisateurs de Skype entreprise online.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Application de groupe de réponse, application de parc d’appels et capture d’appel de groupe

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Un appelant peut entendre une seconde de la musique lors de l’établissement d’un appel avec la fête de l’extraction

<div class="">


> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

**Émet**

Lorsqu’un appel est récupéré par le biais d’un appel de groupe, l’appelant peut entendre une seconde de la musique lors de l’établissement de l’appel avec la partie du récupérateur.

**Moyens**

Il n’existe aucune solution de contournement pour ce problème.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Un agent Response Group peut se connecter et se déconnecter de la console de l’agent Lync Server 2010 aux groupes d’agents officiels Lync Server 2010

**Émet**

Un agent Response Group de Lync Server 2013 peut se connecter et se déconnecter par le biais d’une console de l’agent Lync Server 2010 aux groupes d’agents officiels Lync Server 2010. Dans la console de l’agent Lync Server 2010, les utilisateurs peuvent uniquement voir le groupe de réponse Lync Server 2010 auquel ils appartiennent. Ils ne peuvent pas voir les groupes de réponse Lync Server 2013 auxquels ils appartiennent.

**Moyens**

Si l’agent Response Group est un utilisateur de Lync Server 2013 et fait partie d’un groupe d’agents officiels de Lync Server 2013, l’utilisateur doit accéder à la console de l’agent Lync Server 2013 directement via un lien Web dans un navigateur pour vous connecter et se déconnecter des groupes d’agents Lync Server 2013.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Un agent Response Group de Lync Server 2010 ne peut pas passer d’appels pour le compte d’un groupe de réponse 2013 Server

**Émet**

Un utilisateur de Lync Server 2010 qui est un agent d’un groupe de réponse 2013 Server n’est pas en mesure de passer un appel au nom du groupe de réponse. Le groupe de réponse Lync Server 2013 ne sera pas disponible dans le client Lync pour effectuer un appel.

**Moyens**

Pour contourner ce problème, vous devez déplacer l’utilisateur de Lync Server 2010 vers Lync Server 2013.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>La suppression d’un groupe réponse de Lync Server 2010 après la migration vers Lync Server 2013 empêche le groupe de réponse d’accepter les appels entrants.

**Émet**

Si un groupe Response migration de Lync Server 2010 vers Lync Server 2013 est supprimé de Lync Server 2010 par le biais du panneau de configuration de Lync Server ou de Lync Server Management Shell, le groupe réponse dans Lync Server 2013 cessera de recevoir des appels entrants.

**Moyens**

Pour contourner ce problème, ne supprimez pas les groupes de réponses de Lync Server 2010 qui ont été migrés de Lync Server 2010 vers Lync Server 2013.

Si le groupe de réponse a déjà été supprimé, vous devez le redéployer dans Lync Server 2013.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Lorsqu’un nouveau flux de travail géré est défini sur inactif lors de sa création, le déploiement du flux de travail échoue

**Émet**

Lorsqu’un nouveau flux de travail géré est défini sur inactif lors de sa création, le déploiement du flux de travail échoue. Ce problème survient lorsque le flux de travail est défini sur inactif lors de sa création, mais n’affecte pas le flux de travail modifié pour le définir comme inactif après le déploiement de.

**Moyens**

Lorsque vous créez et déployez un flux de travail, définissez le flux de travail comme actif, puis déployez-le. Après le déploiement réussi du flux de travail, le flux de travail peut être modifié et défini comme inactif.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>Le fait de supprimer un groupe de réponses de la liste de propriétaires empêche le groupe de réponse du pool de sauvegarde d’accepter les appels entrants lors du basculement si le groupe de réponse a été importé dans le pool de sauvegarde

**Émet**

Si un groupe de réponses possédé par le pool principal a été importé dans le pool de sauvegarde sans remplacer le propriétaire, et si le groupe de réponses est supprimé de la liste de propriétaires, le groupe réponse dans le pool de sauvegarde n’accepte aucun appel entrant lors du basculement.

**Moyens**

Vous devez redéployer le groupe Response dans le pool principal. Vous devrez alors exporter la configuration de groupe de réponse à partir du pool principal et l’importer dans le pool de sauvegarde.

Vous pouvez également recréer le groupe Response dans le pool de sauvegarde. Dans ce cas, le pool de sauvegarde sera le pool de propriétaires du groupe de réponse.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>Un appel parqué ne peut pas être récupéré à partir de l’application de parc d’appels si la demande de récupération est exécutée au nom d’un groupe de réponse.

**Émet**

Lorsque les conditions suivantes sont vraies, une demande de récupération d’un appel en stationnement échoue :

  - Un agent fait partie d’un groupe de réponse anonyme

  - L’agent tente de récupérer un appel parqué à partir de l’application de parc d’appels via le groupe de réponse anonyme

  - L’agent tente de récupérer l’appel en composant le numéro orbite par le biais de l’option appeler de la part ou de la même option dans le client attendant Lync.

**Moyens**

Il n’existe aucune solution de contournement pour ce problème. L’appel parqué doit être récupéré sans action pour le compte d’un groupe de réponse.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Panneau de configuration Lync Server, générateur de topologie et outil de planification

<div>

## <a name="planning-tool-limitations"></a>Limitations de l’outil de planification

<div class="">


> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

**Émet**

Lorsque vous planifiez votre déploiement, l’outil de planification présente les limitations suivantes :

  - La prise en charge de 10 sites centraux est au maximum

  - Chaque site central peut comporter un maximum de 14 sites de succursales

  - Chaque site central peut avoir un maximum de 240 000 utilisateurs

Par ailleurs, l’outil de planification n’inclut pas de valeurs pour les éléments suivants lors du calcul de la topologie recommandée :

  - Le nombre d’utilisateurs hébergés en ligne

  - Pourcentage d’utilisateurs activés pour la Fédération XMPP

  - Pourcentage d’utilisateurs qui utilisent Lync Web App

**Moyens**

Il n’existe aucune solution de contournement pour ces problèmes. Pour plus d’informations sur l’outil de planification, voir [conception de la topologie pour Lync Server 2013 à l’aide de l’outil de planification](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>L’outil de planification n’utilise pas les adresses IP précédemment définies pour le réseau Edge lors de la mise à jour des options

**Émet**

Lorsque vous avez terminé de créer votre conception à l’aide de l’outil de planification, si vous apportez des modifications aux options du réseau Edge, des adresses IP supplémentaires pourront être ajoutées à la conception au lieu de mettre à jour les adresses IP existantes. Cela peut se produire lorsque vous affichez les détails du réseau de tâches latérales, sélectionnez **cliquez ici pour mettre à jour vos options**, puis, dans la boîte de dialogue Options de configuration, sélectionnez réseau de bord, sélectionnez **l’option je souhaite utiliser les mêmes noms de domaine complets et adresses IP, mais des ports différents pour les services Edge sur le serveur Edge**. L’application de toute modification entraîne l’ajout de nouvelles adresses IP et de serveurs de frontière à la conception.

**Moyens**

Pour le moment, il n’existe aucune solution de contournement pour ce problème.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>Dans le panneau de configuration de Lync Server, « déplacer tous les utilisateurs vers le pool » risque de ne pas fonctionner comme prévu

**Émet**

Lorsque vous utilisez le panneau de configuration de Lync Server pour déplacer tous les utilisateurs d’un pool vers un autre dans un environnement Active Directory complexe (par exemple, un avec plusieurs contrôleurs de domaine et domaines parent/enfant), un message d’erreur peut être retourné, car « l’utilisateur spécifié n’est pas un utilisateur hérité, utilisez l’applet de commande Move-CsUser à la place. » Cela résulte de temps de réplication plus longs dans les environnements Active Directory complexes.

**Moyens**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Utilisez les filtres du panneau de configuration de Lync Server pour rechercher des utilisateurs hérités, sélectionnez ces utilisateurs, puis utilisez la **commande déplacer les utilisateurs sélectionnés vers le pool** au lieu de **déplacer tous les utilisateurs vers le pool**.

  - Utilisez Lync Server Management Shell pour déplacer des utilisateurs hérités par lot à l’aide d’applets de commande Lync Server.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Le panneau de configuration de Lync Server cesse de fonctionner dans un environnement VMware après la mise à jour du plug-in de navigateur Microsoft Silverlight vers la version 5

**Émet**

Si vous utilisez le panneau de configuration de Lync Server dans un environnement VMware, il est possible que le panneau de configuration de Lync Server cesse de fonctionner après la mise à niveau de Silverlight vers la version 5.

**Moyens**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Désinstaller Silverlight 5, puis installer Silverlight 4 à [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)partir de.

  - Ouvrez le panneau de configuration de Lync Server à partir d’un ordinateur qui n’est pas un ordinateur virtuel VMware.
    
    Pour ouvrir le panneau de configuration de Lync Server à partir d’un ordinateur distant, installez les outils d’administration de Lync Server sur votre ordinateur, puis démarrez le panneau de configuration de Lync Server à partir du menu **Démarrer** de Windows.
    
    Vous pouvez également ouvrir le panneau de configuration de Lync Server en entrant l’URL dans un navigateur Web. L’URL sera similaire à celle du\<nom\_de\_domaine\>complet du pool https:///CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Un administrateur ne peut pas exécuter l’applet de création de désinstallation-csMirrorDB après la suppression de la base de données en miroir dans le générateur de topologie

**Émet**

Lorsqu’un administrateur désactive une base de données en miroir dans le générateur de topologie, puis supprime la base de données en miroir dans le générateur de topologie, un message s’affiche dans la liste des tâches pour l’administrateur pour exécuter l’applet de l’applet de suppression **-csMirrorDatabase** et supprimer la mise en miroir de SQL Server. Lorsque l’administrateur tente d’exécuter l’applet de cmdlet, il échoue.

**Moyens**

Pour supprimer la mise en miroir SQL d’un pool dans le générateur de topologie, vous devez commencer par utiliser une applet de cmdlet pour supprimer le miroir dans SQL Server. Vous pouvez ensuite utiliser le générateur de topologie pour supprimer le miroir de la topologie. Pour supprimer le miroir dans SQL Server, utilisez l’applet de commande suivante :

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Par exemple, pour supprimer la mise en miroir et supprimer les bases de données pour les bases de données utilisateur, tapez ce qui suit :

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Le paramètre *DropExistingDatabasesOnMirror* vous permet de supprimer les bases de données affectées du miroir. Ensuite, pour supprimer le miroir de la topologie, procédez comme suit :

1.  Dans le générateur de topologie, cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

2.  Désactivez l’option **activer la mise en miroir du magasin SQL** , puis cliquez sur **OK**.

3.  Publiez la topologie.

<div class="">


> [!IMPORTANT]  
> Lorsque vous modifiez une relation de mise en miroir de la base de données principale, vous devez redémarrer tous les serveurs frontaux de la liste.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Les erreurs de validation sont renvoyées dans le générateur de topologie lorsqu’un administrateur tente de supprimer un déploiement avec un pool frontal qui dispose d’un magasin témoin associé.

**Émet**

Si un administrateur tente d’utiliser la commande **supprimer le déploiement** dans le générateur de topologie pour supprimer un déploiement incluant un pool frontal avec un magasin témoin associé, une erreur de validation s’affiche dans le générateur de topologie et l’action ne se poursuit pas.

**Moyens**

Pour contourner ce problème, effectuez l’une des opérations suivantes :

  - Supprimez le magasin témoin avant d’essayer de supprimer le déploiement.

  - Ajoutez un magasin témoin pour le pool frontal, puis supprimez-le.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>Les informations de déploiement permanent du serveur de conversation ne sont pas cohérentes entre l’outil de planification et le générateur de topologie

**Émet**

Lorsque le serveur Lync Server 2013, l’outil de planification génère le diagramme de topologie de site pour un déploiement de serveur Chat permanent avec l’option de reprise après sinistre activée, le diagramme de topologie de site inclut plusieurs sites (physiques), avec des serveurs de chat permanent assignés Sitemap. Dans le générateur de topologie, tous les serveurs de chat permanent sont représentés comme appartenant à un site unique (logique) et apparaissent sous le même nœud de pool de serveurs de chat permanent.

**Moyens**

Pour le moment, il n’existe aucune solution de contournement pour ce problème. L’utilisateur doit analyser la sortie de l’outil de planification pour le déploiement de serveur Chat permanent et modifier le plan en fonction de ses besoins spécifiques.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Localisation

<div>

## <a name="monitoring"></a>Surveillance

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>L’Assistant Déploiement des rapports de surveillance affiche des caractères incorrects dans certaines circonstances lors de l’utilisation de la version d’Asie orientale de Lync Server

**Émet**

Lorsque vous utilisez une version d’Asie orientale de Lync Server 2013 (par exemple, chinois (simplifié), chinois (traditionnel), japonais ou coréen, sur un système d’exploitation dont les paramètres régionaux du système ne sont pas définis sur une langue d’Asie de l’est, l’Assistant Déploiement des rapports d’analyse Affichez des points d’interrogation ou d’autres caractères au lieu de messages localisés.

**Moyens**

Pour résoudre ce problème, définissez les paramètres régionaux pour le système d’exploitation et Lync Server 2013 dans la même langue, ce qui permet d’afficher tous les messages correctement.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Panneau de configuration Lync Server

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>Dans certains cas, le premier élément de la barre de navigation supérieure sur une page du panneau de configuration de Lync Server disparaît lorsque vous cliquez sur le dernier élément de la barre de navigation supérieure.

**Émet**

Il existe trois cas connus où cliquer sur le dernier élément de la barre de navigation supérieure sur une page du panneau de configuration de Lync Server entraîne la disparition du premier élément dans la barre de navigation supérieure :

  - Dans la version française, sur la page « Féderation et accès extern », l’élément « stratégie d’accès externe » disparaîtra lorsque vous cliquez sur « partenaires fédérés XMPP ».

  - Dans la version allemande, sur la page « clients », l’élément « Clientversionskonfiguration » disparaît lorsque vous cliquez sur « Pushbenachrichtigungskonfiguration ».

  - Dans la version russe, sur la page « Конфигурация сети », l’élément « Глобально » disparaît lorsque vous cliquez sur « Маршрут региона ».

**Moyens**

Pour contourner ce problème, actualisez la page du panneau de configuration de Lync Server dans votre navigateur. La page se charge dans le navigateur avec tous les éléments dans la barre de navigation supérieure affichée.

</div>

</div>

<div>

## <a name="address-book"></a>Carnet d’adresses

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>L’indexation dans le carnet d’adresses ne fonctionne pas comme prévu dans certaines langues

<div class="">


> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

Si les propriétés d’un utilisateur contiennent un champ indexé et que ce champ ne contient que des caractères qui ne peuvent pas être indexés, l’utilisateur n’apparaît pas dans les recherches effectuées dans le carnet d’adresses.

Les caractères et valeurs locales suivants ne peuvent pas être indexés :

  - Caractères cyrilliques, grecs et arméniens en majuscules

  - Caractères en majuscules accentués

  - Thaï

  - Laos

  - Birmanie

  - DÉVANÂGARÎ

  - Éthiopienne

  - Voyelle

  - Bengali

  - Gujarâtî

  - Telugu

  - Tous les autres scripts Indiens

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, Web Scheduler et composants Web

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>La langue de secours pour certaines langues dans Lync Web Scheduler, le lanceur de la Conférence rendez-vous, la gestion des salles de conversation permanente et OCTab peut ne pas fonctionner comme prévu

**Émet**

Lors de la sélection d’un paramètre régional neutre dans un navigateur Web (dans Internet Explorer, par exemple, le nom de la langue sans spécification \[supplémentaire\](par exemple, « norvégien no ») au lieu d’un paramètre régional spécifiant la langue, le script et les \[paramètres régionaux (\]par exemple, « norvégien, Bokmål (Norvège) NB-no ») peut entraîner un comportement inattendu pour certaines langues dans Lync Web Scheduler, le lanceur d’appels, la gestion des salles de conversation permanentes Par exemple, les utilisateurs peuvent voir la page en anglais lorsque l’une des langues suivantes est sélectionnée :

  - Norvégien

  - Portugais

  - Serbe

**Moyens**

Si vous voulez sélectionner une langue à l’aide d’un paramètre régional neutre, assurez-vous également d’ajouter la langue avec des paramètres régionaux spécifiques (avec l’indicatif de script et/ou du pays) comme langue supplémentaire dans la liste des préférences linguistiques de votre navigateur.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>La prise en charge des paramètres régionaux azéri et ouzbek est limitée lors de l’utilisation de Lync Web Scheduler, de la Conférence rendez-vous, du lanceur de jointure, de la gestion des salles de conversation permanentes et de OCTab dans certains navigateurs Web

<div class="">


> [!NOTE]  
> Les informations de cette section font partie des mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

**Émet**

Lorsque vous utilisez Internet Explorer 8 ou Internet Explorer 9 et que vous définissez la langue du navigateur sur azéri (latin) ou ouzbek (latin), les pages de lancement et de connexion sont affichées en anglais ou dans la langue par défaut définie dans le navigateur.

Lorsque vous utilisez les navigateurs Firefox ou chrome et que vous définissez la langue du navigateur sur azéri (latin) ou ouzbek (latin), les langues Lync Web App, Lync Web Scheduler et RGS OCTab apparaissent en anglais ou dans la langue par défaut du navigateur.

Les paramètres régionaux ouzbek (latin) ne sont pas pris en charge dans le navigateur Safari.

**Moyens**

Il n’existe aucune solution de contournement pour ces problèmes.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>La flèche déroulante ne figure pas dans la liste « rejoindre la réunion de » dans la version roumaine de Lync Web App

**Émet**

Lorsqu’un utilisateur qui utilise la version roumaine de Lync Web App effectue les étapes suivantes, la flèche déroulante ne s’affiche pas dans la liste déroulante **joindre la réunion** dans la liste déroulante :

1.  Sélectionnez **Mémoriser mon adresse sur cet ordinateur** sous l’onglet **général** .

2.  Sélectionnez l’onglet **téléphone** .

3.  Cliquez sur la liste déroulante pour **participer à une réunion à partir de**.
    
    Les utilisateurs ne verront pas une flèche indiquant qu’il existe d’autres options que la connexion par défaut de **Lync Web App**, par exemple : **ne pas participer** à la partie audio (en Roumanie, « nu se asociažae » et **nouveau numéro**» (en Roumanie, « număr Nou »).

**Moyens**

Même si la flèche de cette liste déroulante n’est pas affichée, les utilisateurs peuvent toujours sélectionner les paramètres supplémentaires dans la liste en cliquant sur la valeur par défaut.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Lors de l’utilisation de la version turque de Lync Web Scheduler, une réunion ne peut pas être enregistrée lors de l’utilisation de l’option « personnes que je choisis » sous « qui est présentateur »

**Émet**

Lors de la création ou de la modification d’une réunion dans la version turque de Lync Web Scheduler, l’option « les personnes que je choisis » sous « qui est présentateur » n’est pas prise en charge. Lorsque cette option est sélectionnée, la réunion ne peut pas être enregistrée. Au lieu de cela, un message d’erreur s’affiche, indiquant qu’une ou plusieurs personnes ne peuvent pas être transformées en présentateurs.

**Moyens**

Pour contourner ce problème, les utilisateurs peuvent utiliser l’option par défaut « utilisateurs de ma société » ou tout autre choix, tels que « uniquement organisateur » ou « tout le monde, y compris les personnes externes à mon entreprise ». L’organisateur peut rétrograder ou promouvoir les utilisateurs à leurs rôles appropriés ultérieurement, après avoir rejoint la réunion.

Par ailleurs, les utilisateurs qui comprennent une autre langue peuvent modifier la sélection de la langue dans le navigateur pour l’une des autres langues prises en charge par 43 et tenter d’utiliser l’option « les personnes que je choisis ».

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Reproduction

Ce document prend en charge une version préliminaire d’un produit logiciel dont le changement est susceptible d’être sensiblement antérieur à la version commerciale finale et qui est confidentiel et commercial. Il est divulgué par le biais d’un accord de non-divulgation entre le destinataire et Microsoft. Ce document est fourni à titre indicatif uniquement et Microsoft ne fournit aucune garantie, expresse ou implicite, dans ce document. Les informations contenues dans ce document, y compris les URL et autres références de site Web Internet, peuvent faire l’objet de modifications sans préavis. Le risque qu’une utilisation ou des résultats de l’utilisation de ce document reste l’utilisateur. Sauf mention contraire, les sociétés, organisations, produits, noms de domaines, adresses de messagerie, logos, personnes, lieux et événements décrits dans les exemples ci-dessous sont fictifs. Il n’est pas possible d’associer une société, une organisation, un produit, un nom de domaine, une adresse de messagerie, un logo, une personne, un lieu ou un événement. Conformément à toutes les lois applicables en matière de copyright, il incombe à l’utilisateur. Sans limitation des droits découlant du droit d’auteur, aucune partie de ce document ne pourra être reproduite, stockée ou introduite dans un système de récupération, ni transmise à l’aide d’un moyen quelconque (électronique, mécanique, photocopie, enregistrement ou autre), ou à d’autres fins, sans l’autorisation expresse écrite de Microsoft Corporation.

Microsoft peut être doté d’un brevet, d’une demande de brevet, de marques commerciales, de droits d’auteur ou d’autres droits de propriété intellectuelle concernant le sujet figurant dans ce document. À l’exception de ce que prévoit expressément un contrat de licence écrit de la part de Microsoft, la fourniture de ce document ne vous donne aucune licence pour ces brevets, marques commerciales, droits d’auteur ou toute autre propriété intellectuelle.

© 2012 de Microsoft Corporation. Tous droits réservés.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook et SQL Server sont des marques commerciales ou des marques commerciales déposées de Microsoft Corporation aux États-Unis et/ou dans d’autres pays ou régions.

Toutes les autres marques déposées sont la propriété de leurs détenteurs respectifs.

</div>

</div>

<span> </span>

</div>

</div>

</div>

