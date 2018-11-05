---
title: Processus de migration - Détails
TOCTitle: Processus de migration - Détails
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205264(v=OCS.15)
ms:contentKeyID: 49298858
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de migration - Détails

 

_**Dernière rubrique modifiée :** 2016-12-08_

Utilisez les conditions préalables et les étapes détaillées suivantes pour migrer Lync Server 2010, conversation de groupe ou Office Communications Server 2007 R2  Group Chat vers Lync Server 2013, serveur de conversations permanentes.

## Conditions préalables pour la migration

Veillez à satisfaire les conditions préalables suivantes avant de migrer Lync Server 2010, conversation de groupe ou Office Communications Server 2007 R2  Group Chat vers Lync Server 2013,  serveur de conversations permanentes.

1.  Déployez au moins un pool Lync Server 2013. Si vous avez plusieurs pools Lync Server 2013, déterminez quel pool Lync Server 2013 accueillera le nouveau pool de serveurs de conversations permanentesLync Server 2013.

2.  Installez le pool de serveurs de conversations permanentesLync Server 2013. Il sera vide (pas de catégorie, de salle et de complément). Avant de migrer vos catégories, salles ou compléments hérités, vous pouvez créer des salles, des catégories ou des compléments dans votre déploiement de serveur de conversations permanentesLync Server 2013.
    
    > [!IMPORTANT]  
    > Notez que ces éléments nouvellement créés peuvent entrer en conflit avec les éléments hérités que vous migrez. Évitez tout conflit de nom, sans quoi ils seront remplacés à la migration des données héritées.

## Préparation des données sources pour la migration

Pour préparer correctement vos données sources pour la migration, procédez comme suit.

1.  Sauvegardez les bases de données source pour Lync Server 2010, conversation de groupe ou Office Communications Server 2007 R2 Group Chat. Pour plus d’informations sur la sauvegarde de SQL Server, reportez-vous à « Vue d’ensemble de la sauvegarde (SQL Server) » à l’adresse <http://go.microsoft.com/fwlink/p/?linkid=254851>.
    
    > [!IMPORTANT]  
    > Les services de domaine Active Directory doivent être identiques. Condition pour la migration, vous ne pouvez pas effectuer de migration vers un pool dans un déploiement différent (en particulier, dans une forêt Active Directory différente).

2.  Inspectez la configuration de vos salles de conversation et catégories Lync Server 2010, conversation de groupe ou Office Communications Server 2007 R2  Group Chat. Toutes les modifications des catégories, salles ou compléments dans votre déploiement hérité existant seront apportées par l’outil d’administration Group Chat.
    
    > [!TIP]  
    > Toutes les modifications des catégories, salles ou compléments dans votre déploiement de serveur de conversations permanentesLync Server 2013 sont apportées par le Panneau de configuration Lync Server ou les applets de commande Windows PowerShell.    
    Pour préparer votre système hérité pour la migration, procédez comme suit.
    
    1.  Le serveur de conversations permanentes prend en charge un seul niveau de catégories, et non un ensemble hiérarchique de catégories. Après la migration, les sous-catégories sont précédées du nom complet de la catégorie parent. Vous pouvez simplifier votre structure de catégories existante afin que la structure qui en résulte satisfasse vos conditions.
    
    2.  Vérifiez les **responsables** dans la catégorie racine. Si des responsables existent à ce niveau, ces utilisateurs seront ajoutés en tant que **responsables de toutes les salles** après la migration. S’il ne s’agit pas d’un impératif pour votre organisation, vous devez supprimer ces responsables de la catégorie racine.
    
    3.  Vérifiez la longueur des noms de salle. Après la migration, en raison des structures de catégories simplifiées, si les salles existent sous une catégorie enfant, elles sont précédées du nom complet de la catégorie parent. Les noms peuvent inclure jusqu’à 256 caractères (nom de la catégorie parent inclus). Vous devez vérifier la longueur des noms de salle et éventuellement les raccourcir s’ils sont trop longs.
    
    4.  Dans Lync Server 2013, si les paramètres des **invitations** de catégorie sont définis sur true, vous pouvez choisir true ou false pour les invitations aux salles sous cette catégorie. Cependant, si les paramètres des invitations de catégorie sont définis sur false, les invitations des salles sous cette catégorie sont désactivées. Avant la migration, vous devez réinitialiser les paramètres des invitations dans votre version de Lync Server  serveur Group Chat héritée, si vous voulez qu’une ou plusieurs salles existent sous une catégorie spécifique. Sinon, durant la migration, Lync Server 2013 affiche des avertissements et définit les salles sur la valeur false par défaut.
    
    5.  Si vous avez utilisé des fichiers dans les salles de conversation, vous devez copier manuellement (XCOPY) les fichiers vers le nouveau magasin de fichiers conversation permanente après la migration (les outils ne peuvent pas effectuer cette opération).
    
    6.  Si vous aviez des utilisateurs fédérés et des salles avec des utilisateurs fédérés, notez que le serveur de conversations permanentes ne prend pas en charge la fédération. Les salles avec des utilisateurs fédérés seront migrées. Les utilisateurs ne pourront toutefois pas accéder au contenu, car l’accès fédéré n’est pas pris en charge.
    
    7.  Identifiez les salles que vous ne voulez pas migrer, et marquez-les comme désactivées.
    
    8.  Spécifiez la date après laquelle vous voulez migrer le contenu des salles de conversation. Par exemple, vous pouvez exclure les messages antérieurs au 1er janvier 2010 de la migration, car ceux-ci sont obsolètes ou non appropriés pour la migration.

## Exécution de la migration

Pour migrer votre serveur Group Chat hérité, procédez comme suit.

1.  Arrêtez les services Lync Server 2010, conversation de groupe, Office Communications Server 2007 R2  Group Chat ou Lync Server 2013, serveur de conversations permanentes. Tous les services doivent être arrêtés, aussi, devez-vous planifier cette opération à un moment opportun. Comme décrit précédemment, veillez à sauvegarder votre base de données Group Chat actuelle.

2.  Exécutez l’applet de commande Windows PowerShell**Export-CsPersistentChatData** en tant que membre du rôle RBAC administrateur de conversation permanente (CsPersistentChatAdministrator). Pour plus d’informations sur les applets de commande d’exportation/importation, reportez-vous à [Résolution des problèmes de configuration d’un serveur de conversation permanente avec les applets de commande Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Inspectez le contenu exporté.

3.  Avant l’importation, arrêtez les services Lync Server 2013, serveur de conversations permanentes. Tous les services doivent être arrêtés, aussi, devez-vous planifier cette opération à un moment opportun.

4.  Effectuez une sauvegarde de la base de données conversation permanente si vous avez créé des catégories, des salles ou des compléments dans votre déploiement de Lync Server 2013 avant la migration. Le processus d’exportation/importation pourra fusionner les données héritées dans le déploiement de Lync Server 2013, mais il est recommandé de sauvegarder la base de données au cas où ce contenu est remplacé par accident (par exemple, si des conflits de nom existent encore).

5.  Exécutez l’applet de commande Windows PowerShell**Import-CsPersistentChatData** (outil d’importation), avec une commande **WhatIf** pour renseigner le serveur principal du pool de serveurs de conversations permanentes avec les données migrées. Certaines conversions surviennent dans le processus pour prendre en charge le modèle d’administration simplifié. Corrigez les erreurs et avertissements qui s’affichent.

6.  Exécutez l’applet de commande serveur de conversations permanentesWindows PowerShell**Import-CsPersistentChatData** en tant que membre du rôle RBAC administrateur de conversation permanente (CsPersistentChatAdministrator). Pour plus d’informations sur les applets de commande d’exportation/importation, reportez-vous à [Résolution des problèmes de configuration d’un serveur de conversation permanente avec les applets de commande Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Vous devez copier (XCOPY) tous les fichiers chargés (dossier entier) vers le nouveau magasin de fichiers Lync Server 2013, conversation permanente.
    
    > [!IMPORTANT]  
    > Le client Lync 2013 ne prend pas en charge le téléchargement ou l’affichage de fichiers dans les salles de conversation. Vous pouvez toujours utiliser le client hérité pour publier et afficher les fichiers dans la salle.

8.  Liez l’URI de serveur de recherche Lync Server 2010, conversation de groupe ou Office Communications Server 2007 R2  Group Chat à l’objet contact Lync Server 2013, serveur de conversations permanentes. Les étapes suivantes sont requises si vos clients Conversation de groupe Lync 2010 ou Office Communicator 2007 R2  Group Chat doivent se connecter au client Lync 2013, conversation permanente le plus récent après la migration sans modification de configuration côté client :
    
      - Supprimez le compte d’utilisateur du serveur de recherche ocschat@ *\<nom\_domaine\>* .com. Celui-ci était utilisé pour pointer vers le service de recherche dans Lync Server 2010, conversation de groupe. Vous pouvez désinstaller le pool et supprimer les entrées approuvées plus tard.
    
      - Créez un point de terminaison hérité (objet contact de serveur de conversations permanentes) en exécutant l’applet de commande Windows PowerShell**New-CsPersistentChatEndpoint** avec l’URI SIP identique afin que le client hérité fonctionne de manière efficace lorsque le service est redémarré.
    
    Le processus de migration obligatoire est terminé à ce point. Conversation de groupe Lync 2010 (clients) ou Office Communicator 2007 R2Group Chat (clients) peut maintenant se connecter au nouveau pool de serveurs de conversations permanentes, de manière transparente.
    
    Suivez les étapes de désactivation suivantes pour Lync Server 2010, conversation de groupe ou Office Communications Server 2007 R2Group Chat.

9.  Démarrez les services de serveur de conversations permanentes en allumant tous les ordinateurs dans le nouveau pool de serveurs de conversations permanentes.

10. Utilisez le Panneau de configuration Lync Server et les applets de commande Windows PowerShell pour vérifier que les données ont été correctement migrées.

11. Désinstallez Conversation de groupe Lync 2010 ou Office Communicator 2007 R2Group Chat des ordinateurs dans le pool du serveur Group Chat.

12. Supprimez l’application approuvée et le pool d’applications approuvées à l’aide des applets de commande Windows PowerShell. Cela permet de supprimer ces éléments du magasin central de gestion et les entrées de service approuvé d’Active Directory. Cette étape peut également être effectuée à l’aide du Générateur de topologie (les applications/pools approuvés y ont un nœud dédié également).

13. Vous pouvez maintenant commencer à activer les fonctionnalités de serveur de conversations permanentes via les nouveaux clients. Pour plus d’informations sur l’activation du serveur de conversations permanentes, reportez-vous à [Déploiement d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    > [!IMPORTANT]  
    > Lync Server 2013 prend en charge plusieurs pools de serveurs de conversations permanentes. La migration d’un pool Conversation de groupe Lync 2010 ou Office Communications Server 2007 R2  Group Chat vers un seul pool de serveurs de conversations permanentesLync Server 2013 est toutefois prise en charge. Vous pouvez ajouter de nouveaux pools de serveurs de conversations permanentes dans votre déploiement pour satisfaire les besoins réglementaires (par exemple, conserver les données au sein d’une région donnée).
