---
title: "Conf. du transf. de fich. et du filtr. des URL pour mess. inst. dans LS 2013"
TOCtitle: "Conf. du transf. de fich. et du filtr. des URL pour mess. inst. dans LS 2013"
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520952(v=OCS.15)
ms:contentKeyID: 49296294
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du transfert de fichiers et du filtrage des URL pour la messagerie instantanée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

L’outil Filtre de message instantané intelligent vous aide à protéger votre déploiement de Lync Server 2013 contre les formes de virus les plus courantes, sans que votre utilisation du logiciel n’en soit vraiment affectée. Utilisez le Filtre de message instantané intelligent pour configurer les filtres de façon à bloquer les messages instantanés non sollicités ou potentiellement dangereux en provenance de systèmes d’extrémité inconnus externes au pare-feu d’entreprise. Lors de la configuration des filtres, vous devez spécifier les critères à utiliser pour déterminer les éléments qui doivent être bloqués, tels que les messages instantanés contenant des liens hypertexte et des fichiers avec des préfixes et des extensions spécifiques.

Cet outil comporte les filtrages suivants :

  - Filtrage d’URL amélioré

  - Filtrage du transfert de fichiers amélioré

La configuration de l’outil comporte les tâches suivantes :

  - Configuration du filtrage d’URL

  - Configuration du filtrage de transfert de fichiers

## Application des options de filtrage aux messages instantanés

Avant de déployer l’outil Filtre de message instantané intelligent, vous devez savoir comment les options de filtrage sont appliquées lorsque les messages sont acheminés d’un serveur Lync Server 2013 à un autre. L’application de ces options de filtrage s’effectue toujours de la même manière, que les serveurs soient situés à l’intérieur d’une même organisation ou qu’ils soient disséminés dans plusieurs organisations. Cette cohérence s’applique à la façon dont les messages personnalisés et les avertissements sont insérés dans les messages et transmis aux serveurs.

> [!NOTE]  
> Le filtre de message instantané intelligent augmente les besoins en ressources processeur nécessaires au traitement des URL contenues dans un message. Cette augmentation de la demande des ressources processeur a également un impact sur les performances de Lync Server.

La page **Filtre d’URL** du groupe **Messagerie instantanée et présence** dans le Panneau de configuration Lync Server vous permet de bloquer tous les liens hypertexte ou seulement certains et de configurer un avertissement. L’avertissement est inséré au début d’un message instantané qui contient un lien hypertexte lorsque vous choisissez l’option **Envoyer un message d’avertissement** pour **Préfixe de lien hypertexte** .

Lorsqu’un message instantané transite d’un serveur à un autre, les règles générales suivantes s’appliquent :

  - Si un serveur bloque un message instantané (car vous avez activé la case à cocher **Bloquer les URL avec une extension de fichier** dans la page **Filtre d’URL** ou avez choisi l’option **Bloquer les liens hypertexte** pour **Préfixe de lien hypertexte**), un message d’erreur est retourné au client. Les serveurs suivants ne reçoivent pas ce message instantané.

  - Si un serveur (Serveur1) ajoute un avertissement à un message instantané qui contient un lien hypertexte actif, un autre serveur (Serveur2) qui reçoit ce message instantané peut décider, en fonction du lien hypertexte présent dans le message instantané, de bloquer ce dernier ou d’y ajouter un avertissement. Si Serveur2 est configuré de manière à uniquement ajouter un avertissement pour cette URL, l’avertissement ajouté précédemment par Serveur1 est supprimé, et l’avertissement configuré sur Serveur2 est ajouté au début du message instantané.

> [!NOTE]  
> Si vous exécutez Lync Server 2013 dans un environnement mixte, Live Communications Server 2005 avec SP1 est la version minimale requise pour utiliser l’application Filtre de message instantané intelligent. Le Filtre de message instantané intelligent n’est pas pris en charge sur Live Communications Server 2005 sans SP1.

## Filtrage d’URL

Les URL sont filtrées à partir de leur préfixe de lien hypertexte. Voici quelques exemples de préfixes valides :

  - www\*.

  - ftp.

  - http:

Si vous ne configurez pas le filtre de message instantané de sorte qu’il filtre les URL, toutes les URL contenues dans des messages instantanés sont transmises sans modification via le serveur. Si vous configurez le filtre de message instantané de sorte qu’il filtre les URL, les URL dans les messages instantanés sont filtrées en tenant compte des options que vous sélectionnez dans la boîte de dialogue **Modifier le filtre d’URL** ou **Nouveau filtre d’URL**.

  - **Activer le filtre d’URL**   Cette option active le filtrage des URL pour le déploiement global ou le site que vous sélectionnez.

  - **Bloquer les URL avec une extension de fichier**   Le filtre de message instantané bloque toute URL intranet ou Internet active qui contient un fichier avec une extension répertoriée sous **Extensions de types de fichiers à bloquer** dans la boîte de dialogue **Modifier le filtre de fichiers**. Lorsqu’une URL est bloquée, l’expéditeur obtient un message d’erreur. Lorsqu’elle est activée, cette option prévaut sur toutes les autres options de filtrage pour les extensions de fichier définies sous **Extensions de types de fichiers à bloquer**.
    
    > [!IMPORTANT]  
    > Le filtrage des extensions de fichier se limite aux noms de fichier standard. Il se peut que le filtrage ne fonctionne pas en cas d’extensions de fichier imbriquées dans d’autres noms.

Pour configurer le traitement des liens hypertexte dans les conversations par messagerie instantanée, sélectionnez une des options suivantes sous **Préfixe de lien hypertexte** :

  - **Ne pas filtrer**   Les URL dans les messages sont envoyées via le serveur. Lorsque vous choisissez cette option, la zone **Autoriser le message** apparaît. Dans la zone **Autoriser le message**, indiquez l’avis que vous souhaitez insérer au début de chaque message instantané contenant des liens hypertexte. Cet avis peut comporter jusqu’à 65 535 caractères.

  - **Bloquer les liens hypertexte**   La remise des messages instantanés contenant des liens hypertexte actifs est bloquée par Lync Server et l’expéditeur obtient un message d’erreur.

  - **Envoyer un message d’avertissement**   Lync Server autorise les liens hypertexte actifs dans les messages instantanés mais il ajoute un avertissement. Lorsque vous choisissez cette option, la zone **Message d’avertissement** apparaît. Dans la zone **Message d’avertissement**, tapez l’avertissement que vous voulez inclure aux messages instantanés contenant des liens hypertexte valides. Par exemple, cet avertissement peut indiquer les dangers potentiels qu’encourt l’utilisateur s’il clique sur un lien inconnu ou il peut rappeler les stratégies et les conditions pertinentes de votre organisation concernant l’utilisation des liens. L’avertissement peut comporter jusqu’à 65 535 caractères.

Si vous sélectionnez **Bloquer les liens hypertexte** ou **Envoyer un message d’avertissement**, les options suivantes sont disponibles :

  - **Exclure des liens hypertexte intranet locaux**   Le filtre de message instantané bloque uniquement les URL Internet. Les URL correspondant à des emplacements dans votre intranet sont transmises sans modification via le serveur. Toutefois, pour qu’un serveur exécutant Lync Server transmette une URL d’intranet, le site web local auquel elle renvoie doit faire partie de la zone intranet de ce serveur. Pour vérifier les paramètres de zone intranet d’un serveur, voir la procédure « Configuration des paramètres intranet dans Internet Explorer » dans [Modifier le filtre d’URL par défaut](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtrer ces préfixes de liens hypertexte**   Pour choisir les préfixes que vous souhaitez bloquer, cliquez sur **Sélectionner**, puis dans **Sélectionner un préfixe de lien hypertexte**, ajoutez les préfixes à la liste **Préfixes de liens hypertexte**.
    
    Tous les préfixes sauf **href** doivent se terminer par un point ou un point-virgule, ou un astérisque suivi d’un point. Les préfixes valides peuvent contenir n’importe quel caractère du jeu de caractères d’URL valides, à l’exception de l’astérisque (\*). Les caractères d’URL valides sont les suivants : \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~

## Filtrage de transfert de fichiers

Le filtrage de transfert de fichiers concerne les messages instantanés et les conférences. Pour les conférences, ces paramètres concernent la fonctionnalité des documents dans le client Office Live Meeting 2007 et les fonctionnalités de lecture multimédia.

> [!NOTE]  
> Lync Server comporte également des options de configuration du transfert de fichiers. Ces options côté serveur sont fournies en plus des contrôles côté client disponibles dans Lync Server.

Vous pouvez filtrer les transferts de fichiers au cours des conversations par messagerie instantanée lorsque vous utilisez la fonctionnalité des documents dans le client Office Live Meeting 2007 et les fonctionnalités de lecture multimédia pour tous les types de fichiers. Vous pouvez définir les options suivantes pour contrôler les transferts de fichiers :

  - **Activer le filtre de fichier**   Cette option active le filtrage des fichiers pour le déploiement global ou le site que vous sélectionnez.
    
    Lorsque vous activez le filtre de fichiers, vous pouvez choisir l’une des options suivantes dans **Transfert de fichiers** :
    
      - **Bloquer des types de fichiers spécifiques**   Pour spécifier quelles demandes de transfert de fichiers doivent être filtrées par le serveur, spécifiez une liste des extensions de fichiers à bloquer. Les entrées de la liste peuvent comporter n’importe quel caractère standard, à l’exception du caractère générique (\*). Dans le client Office Live Meeting 2007, la fonctionnalité des documents est activée, mais les fichiers avec cette extension ne peuvent pas être téléchargés. Si vous activez la case à cocher **Bloquer les URL avec une extension de fichier** dans les paramètres d’un filtre d’URL répertorié sous l’onglet **Filtre d’URL**, le filtre d’URL utilise cette même liste pour bloquer les liens hypertexte actifs qui contiennent ces extensions de fichier. Pour choisir les types de fichiers que vous souhaitez bloquer, cliquez sur **Sélectionner**, puis dans **Sélectionner un type de fichier**, ajoutez les extensions de type de fichier à la liste **Extensions de types de fichiers sélectionnées**.
    
      - **Bloquer tout**   Le serveur arrête de traiter tous les messages instantanés qui contiennent une demande de transfert de fichiers et retourne un message d’erreur à l’expéditeur de la demande. La fonctionnalité des documents est désactivée dans le client Office Live Meeting 2007.

> [!IMPORTANT]  
> Le filtrage des extensions de fichier se limite aux noms de fichier standard. Il se peut que le filtrage ne fonctionne pas en cas d’extensions de fichier imbriquées dans d’autres noms.

## Dans cette section

  - [Modifier le filtre de transfert de fichiers par défaut](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Créer un filtre de transfert de fichiers pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modifier le filtre d’URL par défaut](lync-server-2013-modify-the-default-url-filter.md)

  - [Créer un filtre d’URL pour gérer les liens hypertexte dans des conversations de messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

## Voir aussi

#### Autres ressources

[Gestion des paramètres de messagerie instantanée et de présence dans Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)

