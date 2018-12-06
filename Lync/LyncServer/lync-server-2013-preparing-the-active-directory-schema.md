---
title: 'Lync Server 2013 : Préparation du schéma Active Directory'
TOCTitle: Préparation du schéma Active Directory
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398119(v=OCS.15)
ms:contentKeyID: 49296136
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation du schéma Active Directory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Avant de commencer à préparer les services de domaine Active Directory, vous pouvez ouvrir les fichiers de schéma à l’aide d’un éditeur de texte, tel que le Bloc-notes de Windows, ou consultez [Attributs, classes et extensions des schémas Active Directory utilisés par Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) pour consulter toutes les extensions de schéma services de domaine Active Directory qui seront modifiées pour Lync Server 2013. Lync Server utilise quatre fichiers de schéma :

  - ExternalSchema.ldf, qui est utilisé pour l’interopérabilité avec Microsoft Exchange Server

  - ServerSchema.ldf, qui est le fichier de schéma Lync Server 2013 principal

  - BackCompatSchema.ldf, qui est utilisé pour l’interopérabilité avec des composants de versions précédentes

  - VersionSchema.ldf, qui est utilisé pour les informations de version du schéma préparé

Tous les fichiers .ldf sont installés au cours de la préparation du schéma, même si vous procédez à une migration depuis une version précédente ou à une nouvelle installation. Ces fichiers de schéma sont installés dans l’ordre indiqué précédemment et se trouvent dans le dossier \\Support\\schema sur le support d’installation.

Les extensions de schéma Lync Server sont répliquées dans tous les domaines, ce qui a un impact sur le trafic réseau. Exécutez la préparation du schéma lorsque l’utilisation du réseau est basse.

> [!NOTE]  
> Si vous devez ajouter la prise en charge de Microsoft® Office Communicator Mobile 2007 R2 pour Java et Microsoft® Office Communicator Mobile pour les clients mobiles Nokia 1.0 à votre déploiement Lync Server 2013, il vous faut préparer le schéma Active Directory pour Microsoft Office Communications Server 2007 R2 lors de l’installation de Lync Server 2013. Pour obtenir la documentation et les logiciels nécessaires, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</a>.

## Éditeur ADSI

L’Éditeur ADSI (Active Directory Service Interfaces) est un outil d’administration AD DS qui vous permet de vérifier la préparation et la réplication du schéma.

L’Éditeur ADSI est installé par défaut lorsque vous installez le rôle AD DS pour faire d’un serveur un contrôleur de domaine. Pour Windows Server 2008 et Windows Server 2008 R2, l’Éditeur ADSI (adsiedit.msc) fait partie des outils d’administration de serveur distant. Vous pouvez également installer les outils d’administration de serveur distant sur des serveurs membres du domaine ou des serveurs autonomes. Le package des outils d’administration de serveur distant est copié par défaut sur ces serveurs lorsque vous installez Windows, mais il n’est pas installé par défaut. Utilisez le Gestionnaire de serveur pour installer chaque outil. L’éditeur ADSI est inclus sous **Outils d’administration de rôles** , **Outils des services de domaine Active Directory** , **Outils de contrôleur de domaine Active Directory** .

Pour Windows Server 2003, l’Éditeur ADSI fait partie des outils de support, disponibles sur le CD Windows Server 2003, dans le dossier \\SUPPORT\\TOOLS. Vous pouvez également les télécharger depuis le site web « Outils de support de Windows Server 2003 Service Pack 2 32 bits » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770).Les instructions d’installation à partir du CD sont disponibles sur le site web «  Installer les outils de support Windows » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771). Adsiedit.dll est inscrit automatiquement lorsque vous installez les outils de support. Cependant, si vous avez copié les fichiers sur votre ordinateur, vous devez exécuter la commande **regsvr32** pour inscrire le fichier adsiedit.dll avant de pouvoir exécuter l’outil.

## Dans cette section

  - [Exécution de la préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

## Voir aussi

#### Autres ressources

[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)

