---
title: Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b741418790c5faf11c566afb27a477a67beb71ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Le filtre de message instantané intelligent permet de protéger votre déploiement Lync Server 2013 contre la propagation des formes les plus courantes de virus, avec une dégradation minimale de l’expérience utilisateur. Utilisez le Filtre de message instantané intelligent pour configurer les filtres de façon à bloquer les messages instantanés non sollicités ou potentiellement dangereux en provenance de systèmes d’extrémité inconnus externes au pare-feu d’entreprise. Lors de la configuration des filtres, vous devez spécifier les critères à utiliser pour déterminer les éléments qui doivent être bloqués, tels que les messages instantanés contenant des liens hypertexte et des fichiers avec des préfixes et des extensions spécifiques.

Cet outil comporte les filtrages suivants :

  - Filtrage d’URL amélioré

  - Filtrage du transfert de fichiers amélioré

La configuration de l’outil comporte les tâches suivantes :

  - Configuration du filtrage d’URL

  - Configuration du filtrage de transfert de fichiers

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Application des options de filtrage aux messages instantanés

Avant de déployer l’outil de filtrage de message instantané intelligent, vous devez comprendre comment les options de filtrage sont appliquées lorsque les messages sont routés d’un serveur Lync Server 2013 à un autre. L’application de ces options de filtrage s’effectue toujours de la même manière, que les serveurs soient situés à l’intérieur d’une même organisation ou qu’ils soient disséminés dans plusieurs organisations. Cette cohérence s’applique à la façon dont les messages personnalisés et les avertissements sont insérés dans les messages et transmis aux serveurs.

<div>


> [!NOTE]
> Le filtre de message instantané intelligent augmente les besoins en ressources processeur nécessaires au traitement des URL contenues dans un message. Cette augmentation de la demande d’UC affecte également les performances de Lync Server.



</div>

À l’aide de la page de **filtrage d’URL** du groupe **messagerie instantanée et présence** dans le panneau de configuration Lync Server, vous pouvez bloquer une partie ou la totalité des liens hypertexte ou configurer un avertissement. L’avertissement est inséré au début d’un message instantané qui contient un lien hypertexte lorsque vous choisissez l’option **Envoyer un message d’avertissement** pour **Préfixe de lien hypertexte** .

Lorsqu’un message instantané transite d’un serveur à un autre, les règles générales suivantes s’appliquent :

  - Si un serveur bloque un message instantané (car vous avez activé la case à cocher **Bloquer les URL avec une extension de fichier** dans la page **Filtre d’URL** ou avez choisi l’option **Bloquer les liens hypertexte** pour **Préfixe de lien hypertexte**), un message d’erreur est retourné au client. Les serveurs suivants ne reçoivent pas ce message instantané.

  - Si un serveur (Serveur1) ajoute un avertissement à un message instantané qui contient un lien hypertexte actif, un autre serveur (Serveur2) qui reçoit ce message instantané peut décider, en fonction du lien hypertexte présent dans le message instantané, de bloquer ce dernier ou d’y ajouter un avertissement. Si Serveur2 est configuré de manière à uniquement ajouter un avertissement pour cette URL, l’avertissement ajouté précédemment par Serveur1 est supprimé, et l’avertissement configuré sur Serveur2 est ajouté au début du message instantané.

<div>


> [!NOTE]
> Si vous exécutez Lync Server 2013 dans un environnement mixte, Live Communications Server 2005 avec SP1 est la version minimale requise pour utiliser l’application de filtre de message instantané intelligent. Le Filtre de message instantané intelligent n’est pas pris en charge sur Live Communications Server 2005 sans SP1.



</div>

<div>

## <a name="url-filtering"></a>Filtrage d’URL

Les URL sont filtrées à partir de leur préfixe de lien hypertexte. Voici quelques exemples de préfixes valides :

  - www\*.

  - serveurFTP.

  - http

Si vous ne configurez pas le filtre de message instantané de sorte qu’il filtre les URL, toutes les URL contenues dans des messages instantanés sont transmises sans modification via le serveur. Si vous configurez le filtre de message instantané de sorte qu’il filtre les URL, les URL dans les messages instantanés sont filtrées en tenant compte des options que vous sélectionnez dans la boîte de dialogue **Modifier le filtre d’URL** ou **Nouveau filtre d’URL**.

  - **Activer le filtre**   d’URL cette option active le filtrage d’URL pour le déploiement global ou pour le site que vous sélectionnez.

  - **Bloquer les URL avec l’extension**   de fichier le filtre de message instantané bloque toute URL Internet ou Internet active qui contient un fichier dont l’extension est indiquée sous **extensions de types de fichiers à bloquer** dans la boîte de dialogue **modifier le filtre de fichier** . Lorsqu’une URL est bloquée, l’expéditeur obtient un message d’erreur. Lorsqu’elle est activée, cette option prévaut sur toutes les autres options de filtrage pour les extensions de fichier définies sous **Extensions de types de fichiers à bloquer**.
    
    <div>
    

    > [!IMPORTANT]
    > Le filtrage des extensions de fichier se limite aux noms de fichier standard. Il se peut que le filtrage ne fonctionne pas en cas d’extensions de fichier imbriquées dans d’autres noms.

    
    </div>

Pour configurer le traitement des liens hypertexte dans les conversations par messagerie instantanée, sélectionnez une des options suivantes sous **Préfixe de lien hypertexte** :

  - **Ne pas filtrer**   les URL dans les messages sont envoyées par le biais du serveur. Lorsque vous choisissez cette option, la zone **Autoriser le message** apparaît. Dans la zone **Autoriser le message**, indiquez l’avis que vous souhaitez insérer au début de chaque message instantané contenant des liens hypertexte. Cet avis peut comporter jusqu’à 65 535 caractères.

  - **Bloquer les liens hypertexte**   la remise de messages instantanés contenant des liens hypertexte actifs est bloquée par Lync Server et un message d’erreur s’affiche pour l’expéditeur.

  - **Envoyer un message**   d’avertissement Lync Server autorise les liens hypertexte actifs dans les messages instantanés, mais il comprend un avertissement. Lorsque vous choisissez cette option, la zone **Message d’avertissement** apparaît. Dans la zone **Message d’avertissement**, tapez l’avertissement que vous voulez inclure aux messages instantanés contenant des liens hypertexte valides. Par exemple, cet avertissement peut indiquer les dangers potentiels qu’encourt l’utilisateur s’il clique sur un lien inconnu ou il peut rappeler les stratégies et les conditions pertinentes de votre organisation concernant l’utilisation des liens. L’avertissement peut comporter jusqu’à 65 535  caractères.

Si vous sélectionnez **Bloquer les liens hypertexte** ou **Envoyer un message d’avertissement**, les options suivantes sont disponibles :

  - **Exclure les liens hypertexte de l’intranet local**   le filtre de messages instantanés bloque uniquement les URL Internet. Les URL correspondant à des emplacements dans votre intranet sont transmises sans modification via le serveur. Toutefois, les URL intranet auxquelles les serveurs individuels exécutant Lync Server sont passés dépendent des types de sites Web locaux considérés comme faisant partie de leur zone intranet. Pour vérifier les paramètres de la zone intranet d’un serveur, reportez-vous à la procédure « pour configurer vos paramètres intranet dans Internet Explorer » dans [modifier le filtre d’URL par défaut dans Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtrez ces**   préfixes de liens hypertexte pour choisir les préfixes à bloquer, cliquez sur **Sélectionner**, puis, dans sélectionner un préfixe de **lien hypertexte**, ajoutez les préfixes à la liste préfixes de **liens hypertexte** .
    
    Tous les préfixes sauf **href** doivent se terminer par un point ou un point-virgule, ou un astérisque suivi d’un point. Les préfixes valides peuvent contenir n’importe quel caractère dans le jeu de caractères d'\*URL valides à l’exception de l’astérisque (). Le jeu de caractères d’URL valides \# \*est : +/0123456789 =\_ \` @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ abcdefghijklmnopqrstuvwxyz | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Filtrage de transfert de fichiers

Le filtrage de transfert de fichiers concerne les messages instantanés et les conférences. Pour les conférences, ces paramètres concernent la fonctionnalité des documents dans le client Office Live Meeting 2007 et les fonctionnalités de lecture multimédia.

<div>


> [!NOTE]
> Lync Server offre également des options de paramètres de transfert de fichiers. Cette option côté serveur est proposée en plus des contrôles côté client disponibles dans Lync Server.



</div>

Vous pouvez filtrer les transferts de fichiers au cours des conversations par messagerie instantanée lorsque vous utilisez la fonctionnalité des documents dans le client Office Live Meeting 2007 et les fonctionnalités de lecture multimédia pour tous les types de fichiers. Vous pouvez définir les options suivantes pour contrôler les transferts de fichiers :

  - **Activer le filtre**   de fichiers cette option active le filtrage de fichiers pour le déploiement global ou pour le site que vous sélectionnez.
    
    Lorsque vous activez le filtre de fichiers, vous pouvez choisir l’une des options suivantes dans **Transfert de fichiers** :
    
      - **Bloquer des types**   de fichiers spécifiques vous spécifiez les demandes de transfert de fichiers filtrées par le serveur en spécifiant une liste d’extensions de fichiers à bloquer. Les entrées de la liste peuvent contenir tous les caractères standard, mais pas le caractère\*générique (). Dans le client Office Live Meeting 2007, la fonctionnalité des documents est activée, mais les fichiers avec cette extension ne peuvent pas être téléchargés. Si vous activez la case à cocher **Bloquer les URL avec une extension de fichier** dans les paramètres d’un filtre d’URL répertorié sous l’onglet **Filtre d’URL**, le filtre d’URL utilise cette même liste pour bloquer les liens hypertexte actifs qui contiennent ces extensions de fichier. Pour choisir les types de fichiers que vous souhaitez bloquer, cliquez sur **Sélectionner**, puis dans **Sélectionner un type de fichier**, ajoutez les extensions de type de fichier à la liste **Extensions de types de fichiers sélectionnées**.
    
      - **Bloquer tout**   le serveur supprime tous les messages instantanés qui contiennent des demandes de transfert de fichiers et renvoie un message d’erreur à l’expéditeur de la demande. La fonctionnalité des documents est désactivée dans le client Office Live Meeting 2007.

<div>


> [!IMPORTANT]
> Le filtrage des extensions de fichier se limite aux noms de fichier standard. Il se peut que le filtrage ne fonctionne pas en cas d’extensions de fichier imbriquées dans d’autres noms.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Créer un nouveau filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modifier le filtre d’URL par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des paramètres de messagerie instantanée et de présence dans Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

