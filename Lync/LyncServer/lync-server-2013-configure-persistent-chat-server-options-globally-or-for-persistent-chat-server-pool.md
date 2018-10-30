---
title: "Lync Server 2013 : Conf. op. de serv. de conv. perm. niv. gl. ou pool de s."
TOCTitle: Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204731(v=OCS.15)
ms:contentKeyID: 49296454
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Dans Panneau de configuration Lync Server 2013, vous pouvez utiliser la section **conversation permanente Configuration** de la page **conversation permanente** pour configurer globalement les paramètres conversation permanente lorsqu’elle s’applique à tous les pools de serveurs de conversations permanentes ou pour un pool de serveurs de conversations permanentes en particulier.

> [!NOTE]  
> Pour configurer et utiliser le serveur de conversations permanentes, vous devez d’abord utiliser le Générateur de topologie pour ajouter la prise en charge du serveur de conversations permanentes à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement.

## Pour configurer les options de conversation permanente globalement

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le Panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de démarrer le Panneau de configuration Lync Server, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell</a> dans la documentation de déploiement.

3.  Dans la barre de navigation de gauche, cliquez sur **conversation permanente**, puis sur **conversation permanente Configuration**.

4.  Dans la page **conversation permanente Configuration**, cliquez sur **Nouveau,** puis sur **Configuration du site**.
    
    > [!IMPORTANT]  
    > Sélectionnez cette option si vous voulez que la configuration soit appliquée à tous les pools de serveurs de conversations permanentes déployés sur le site. Cliquez sur <strong>Configuration du pool</strong> si vous voulez que la configuration soit appliquée à un pool de serveurs de conversations permanentes spécifique.

5.  Dans **Sélectionner un site** , sélectionnez le site à configurer pour la configuration du site de serveur de conversations permanentes.

6.  Dans **Nouvelle configuration conversation permanente**, effectuez les opérations suivantes :
    
      - Dans **Nom** , spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site existe déjà.
    
      - Dans **Historique de conversation par défaut** , définissez le nombre de messages de conversation qui seront traités pour chaque salle lors de la première demande. Par défaut, 30 messages sont traités. Il s’agit du paramètre global par défaut : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
        
        > [!IMPORTANT]  
        > Le serveur de conversations permanentes mettra ces messages en mémoire cache. Par conséquent, si vous augmentez ce nombre, une quantité plus élevée de messages seront mis dans le cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation.    
      - Dans **Taille de fichier maximale (Ko)** , sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale pour un fichier qui peut être téléchargée vers une salle de conversation dans le système (pour lequel les téléchargements de fichiers sont activés par le biais du paramètre **Catégorie** correspondant).
        
        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur car des applications personnalisées ou des clients Group Chat antérieurs utilisant le serveur Group ChatOffice Communications Server 2007 R2 ou Lync Server 2010, conversation de groupe peuvent publier des fichiers dans une salle. Le client Lync 2013 ne dispose pas de fonctionnalités de téléchargement de fichier en amont ou en aval. Par conséquent, si vous avez un client Lync 2013 ou un déploiement Lync 2013 pur, il est impossible de publier des fichiers dans une salle de conversation de serveur de conversations permanentes.    
      - Dans **Limite de mise à jour du participant :** , sélectionnez la limite pour les mises à jour de participants. Le serveur de conversations permanentes envoie des informations (personnes connectées à une salle de conversation) à tous les participants jusqu’à ce que la quantité d’utilisateurs connectés atteigne ce nombre. Par défaut, cette limite est de 75. Elle indique la quantité maximale de participants dans une salle donnée au-delà de laquelle le serveur de conversations permanentes cesse d’envoyer des mises à jour aux clients connectés concernant les personnes présentes dans la salle.
    
      - (Facultatif.) Dans **URL de gestion de salle** , sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’une gestion de salle personnalisée basée sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vierge. Une fois l’URL définie, elle est appliquée comme URL de gestion de salle interne et externe.
        
        Si vous souhaitez personnaliser votre expérience de création de salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion de salle personnalisée à l’aide du Kit de développement logiciel (SDK) de serveur de conversations permanentes, héberger cette solution quelque part et indiquer l’URL à cet emplacement. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.

7.  Cliquez sur **Valider** .

## Pour configurer les options de conversation permanente pour un pool de serveurs de conversations permanentes spécifique

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le Panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de démarrer le Panneau de configuration Lync Server, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell</a> dans la documentation de déploiement.

3.  Dans la barre de navigation de gauche, cliquez sur **conversation permanente**, puis sur **conversation permanente Configuration**.

4.  Dans la page **conversation permanente Configuration**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.

5.  Dans **Sélectionner un service** , sélectionnez le service associé au pool de serveurs de conversations permanentes à configurer.

6.  Dans **Nouvelle configuration conversation permanente**, effectuez les opérations suivantes :
    
      - Dans **Nom** , spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà.
    
      - Dans **Historique de conversation par défaut** , définissez le nombre de messages de conversation qui seront traités pour chaque salle lors de la première demande. Par défaut, 30 messages sont traités. Il s’agit du paramètre global par défaut : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
        
        > [!IMPORTANT]  
        > Le serveur de conversations permanentes mettra ces messages en mémoire cache. Par conséquent, si vous augmentez ce nombre, une quantité plus élevée de messages seront mis dans le cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation.    
      - Dans **Taille de fichier maximale (Ko)** , sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale pour un fichier qui peut être téléchargée vers une salle de conversation dans le système (pour lequel les téléchargements de fichiers sont activés par le biais du paramètre **Catégorie** correspondant).
        
        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur car des applications personnalisées ou des clients Group Chat antérieurs ( serveur Group ChatOffice Communications Server 2007 R2 ou Lync Server 2010, conversation de groupe) peuvent publier des fichiers dans une salle. Le client Lync 2013 ne dispose pas de fonctionnalités de téléchargement de fichier en amont ou en aval. Par conséquent, si vous avez un client Lync 2013 ou un déploiement Lync 2013 pur, il est impossible de publier des fichiers dans une salle de conversation de serveur de conversations permanentes.    
      - Dans **Limite de mise à jour du participant :** , sélectionnez la limite pour les mises à jour de participants. Le serveur de conversations permanentes envoie des informations (personnes connectées à une salle de conversation) à tous les participants jusqu’à ce que la quantité d’utilisateurs connectés atteigne ce nombre. Par défaut, cette limite est de 75. Elle indique la quantité maximale de participants dans une salle donnée au-delà de laquelle le serveur de conversations permanentes cesse d’envoyer des mises à jour aux clients connectés concernant les personnes présentes dans la salle.
    
      - Dans **URL de gestion de salle :** sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vierge.
        
        Si vous souhaitez personnaliser votre expérience de création de salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion de salle personnalisée à l’aide du Kit de développement logiciel (SDK) de serveur de conversations permanentes, héberger cette solution quelque part et indiquer l’URL à cet emplacement. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.

7.  Cliquez sur **Valider** .

