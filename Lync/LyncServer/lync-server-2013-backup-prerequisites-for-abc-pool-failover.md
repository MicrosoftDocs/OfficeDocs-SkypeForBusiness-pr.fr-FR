---
title: Opérations de sauvegarde à effectuer avant un basculement de pool ABC
TOCTitle: Opérations de sauvegarde à effectuer avant un basculement de pool ABC
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945634(v=OCS.15)
ms:contentKeyID: 53095439
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Opérations de sauvegarde à effectuer avant un basculement de pool ABC

 

_**Dernière rubrique modifiée :** 2013-03-26_

Pour tirer le plus grand parti de l’utilisation de la procédure de basculement de pool ABC, vous devez effectuer certaines sauvegardes avant que ne se produisent l’incident et le basculement :

  - Vous devez sauvegarder régulièrement les données de configuration LIS (Location Information Service) à partir du pool A à l’aide de l’applet de commande **Export-CsLISConfiguration**.
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Vous devez sauvegarder régulièrement les données de configuration Response Group dans le pool A à l’aide de l’applet de commande **Export-CsRgsConfiguration**.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    En règle générale, nous vous recommandons d’effectuer des sauvegardes quotidiennes, mais si le volume de vos changements est élevé, vous pouvez planifier des sauvegardes plus fréquentes. La quantité d’informations que vous risquez de perdre en cas d’incident dépend de la fréquence de vos sauvegardes, ainsi que de la fréquence et du volume des changements.
    
    L’application Response Group ne peut stocker qu’un seul jeu de paramètres de niveau application par pool. Ces paramètres sont accessibles par le biais de l’applet de commande **Get-CsRgsConfiguration**. Les paramètres incluent la configuration de la mise en attente musicale, le fichier audio de mise en attente musicale par défaut, la période de grâce de reprise d’appel parqué d’agent et la configuration du contexte de l’appel. Ces paramètres peuvent être transférés depuis un pool vers un autre à l’aide de l’applet de commande **Import-CsRgsConfiguration** et du paramètre **ReplaceExistingSettings**, mais cette opération remplace tous les paramètres de niveau application dans le pool de destination.
    
    > [!TIP]  
    > Dans un emplacement séparé, conservez une copie de sauvegarde de tous les fichiers audio d’origine qui ont servi à la configuration de l’application Response Group (c’est-à-dire les enregistrements ou les fichiers de mise en attente musicale).    
    Si des fichiers de mise en attente musicale personnalisés ont été téléchargés pour le parcage d’appel vers un pool, vous devez en conserver une copie à un autre emplacement. Ces fichiers ne sont pas sauvegardés durant le processus de récupération d’urgence de Lync Server 2013 et seront perdus si les fichiers téléchargés vers le pool sont endommagés ou effacés.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    > [!NOTE]  
    > L’application de parcage d’appel ne peut stocker qu’un seul jeu de paramètres et qu’un seul fichier audio de mise en attente musicale personnalisé par pool. Ces paramètres sont accessibles par le biais de l’applet de commande <strong>Get-CsCpsConfiguration</strong>. Étant donné que le mécanisme de récupération d’urgence du parcage d’appel repose sur l’application de parcage d’appel du pool de sauvegarde, les paramètres du pool principal ne sont pas sauvegardés ou conservés en cas d’incident. Si le pool principal est perdu, ces paramètres ne peuvent pas être récupérés et, quand un nouveau pool est déployé pour remplacer le pool principal, les paramètres du parcage d’appel et tout fichier audio de mise en attente musicale personnalisé doivent être reconfigurés.

  - Si vous configurez des annonces dans le cadre de la fonctionnalité audio de numéro non attribué, nous vous recommandons de conserver à un autre emplacement une copie de tout fichier audio d’origine utilisé pendant la configuration initiale. Si vous n’avez pas effectué cette opération, vous pouvez obtenir une copie des fichiers audio configurés dans le magasin de fichiers du serveur ou du pool vers lequel les fichiers audio ont été importés. Ces fichiers ne sont pas sauvegardés durant le processus de récupération d’urgence de Lync Server 2013 et seront perdus si les fichiers téléchargés vers le pool sont endommagés ou effacés. Pour copier tous les fichiers audio utilisés pour la configuration de la fonctionnalité audio de numéro non attribué à partir du magasin de fichiers d’un serveur ou d’un pool, utilisez la commande suivante :
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Si un pool comporte des bases de données de surveillance et d’archivage, vous devez utiliser les outils de gestion SQL Server pour les sauvegarder. Dans la procédure de basculement ABC, les bases de données de surveillance et d’archivage ne sont pas conservées si elles sont colocalisées dans le pool A, car ces bases de données ne sont pas sauvegardées par le biais du service de sauvegarde de Lync Server.

