---
title: "Lync Server 2013 : Déf. des topo. facult. de directeur dans votre topologie"
TOCTitle: Définition des topologies facultatives de directeur dans votre topologie
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398717(v=OCS.15)
ms:contentKeyID: 49298034
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition des topologies facultatives de directeur dans votre topologie pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Les directeurs Lync Server 2013 peuvent être des serveurs d’instance unique. Ils peuvent aussi être installés en tant que pool de charge équilibrée constitué de plusieurs directeurs pour augmenter la capacité et la disponibilité. L’équilibrage de la charge matérielle et de la charge DNS sont tous deux pris en charge. Cette rubrique explique comment configurer l’équilibrage de la charge DNS pour les pools directeurs.

Pour réussir à publier, activer ou désactiver une topologie lorsque vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes **RTCUniversalServerAdmins** et **Domain Admins** . Vous pouvez également déléguer les droits et autorisations d’administrateur appropriées pour ajouter des rôles serveur. Pour plus d’informations, reportez-vous à [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation du déploiement du serveur Standard Edition ou Enterprise Edition. En ce qui concerne les autres modifications de configuration, seule l’appartenance au groupe **RTCUniversalServerAdmins** est requise.

Cette rubrique décrit les étapes nécessaires pour définir et publier la topologie pour les deux topologies directeur :

  - Pour définir le directeur (instance unique)

  - Pour définir le directeur (pool de plusieurs directeurs)

## Pour définir le directeur (instance unique)

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans la page d’accueil, cliquez sur **Télécharger la topologie à partir du déploiement existant** .

3.  Dans la boîte de dialogue **Enregistrer la topologie sous** , tapez le nom et l’emplacement de la copie locale de la topologie existante, puis cliquez sur **Enregistrer** .

4.  Développez le site dans lequel vous planifiez d’ajouter le directeur, cliquez avec le bouton droit sur **Pools directeurs** , puis cliquez sur **Nouveau pool directeur** .

5.  Dans la boîte de dialogue **Définir le nom de domaine complet du pool directeur** , procédez comme suit :
    
      - Dans **Nom de domaine complet du pool** , tapez le nom de domaine complet du pool directeur.
    
      - Cliquez sur **Pool d’un seul ordinateur** , puis sur **Suivant** .

6.  Dans la boîte de dialogue **Définir le partage de fichiers** , effectuez l’une des opérations suivantes :
    
    1.  Pour utiliser un partage de fichiers existant, cliquez sur **Utiliser un partage de fichiers précédemment défini** , sélectionnez un partage de fichiers dans la liste, puis cliquez sur **Suivant** .
    
    2.  Pour créer un partage de fichiers, cliquez sur **Définir un nouveau partage de fichiers** , tapez le nom de domaine complet de l’emplacement du partage de fichiers dans **Nom de domaine complet du serveur de fichiers** , tapez le nom du partage dans **Partage de fichiers** , puis cliquez sur **Suivant** .
    
    > [!IMPORTANT]  
    > Le partage de fichiers que vous spécifiez ou créez à cette étape doit exister ou être créé avant de publier la topologie.<br />
    Le partage de fichiers attribué à un directeur n’est pas utilisé, si bien que vous pouvez attribuer le partage de fichiers de n’importe quel pool dans l’entreprise.

7.  Dans la boîte de dialogue **Spécifier l’URL des services web** , dans **URL de base externe** , spécifiez le nom de domaine complet des directeurs, puis cliquez sur **Terminer** .
    
    > [!IMPORTANT]  
    > Le nom doit pouvoir être résolu à partir des serveurs DNS Internet et doit pointer vers l’adresse IP publique du proxy inverse. Celui-ci écoute les demandes HTTP/HTTPS envoyées à cette URL et les transmet via le serveur proxy au répertoire virtuel des services web externes sur ce directeur.    
    > [!WARNING]  
    > Si vous installez plus d’un pool de serveurs frontaux ou serveur frontal, le nom de domaine complet (FQDN) des services web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services web externes d’un serveur frontal en tant que <strong>pool01.contoso.com</strong>, vous ne pouvez pas utiliser ce nom <strong>pool01.contoso.com</strong> pour un autre pool de serveurs frontaux ou serveur frontal. Si vous déployez aussi des directeurs, le nom de domaine complet des services web externes défini pour un directeur ou un pool de directeurs doit être différent de tout autre directeur ou pool de directeurs et de tout pool de serveurs frontaux ou serveur frontal existant. Si vous choisissez de remplacer le nom des services web internes par un nom de domaine complet personnalisé, chaque nom de domaine complet doit être distinct des autres noms de pool de serveurs frontaux, directeur ou pool de directeurs.

8.  Publiez la topologie.

## Pour définir le directeur (pool de plusieurs directeurs)

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans la page d’accueil, cliquez sur **Télécharger la topologie à partir du déploiement existant** .

3.  Dans la boîte de dialogue **Enregistrer la topologie sous** , tapez le nom et l’emplacement de la copie locale de la topologie existante, puis cliquez sur **Enregistrer** .

4.  Développez le site dans lequel vous planifiez d’ajouter le directeur, cliquez avec le bouton droit sur **Pools directeurs** , puis cliquez sur **Nouveau pool directeur** .

5.  Dans la boîte de dialogue **Définir le nom de domaine complet du pool directeur** , procédez comme suit :
    
      - Dans **Nom de domaine complet du pool** , tapez le nom de domaine complet du pool directeur.
    
      - Cliquez sur **Pool de plusieurs ordinateurs** , puis sur **Suivant** .

6.  Dans la boîte de dialogue **Définissez les ordinateurs inclus dans ce pool** , procédez comme suit :
    
      - Spécifiez le nom de domaine complet d’ordinateur du premier membre du pool, puis cliquez sur **Ajouter** .
    
      - Répétez l’étape précédente pour chaque ordinateur à ajouter. Lorsque vous avez terminé, cliquez sur **Suivant** .

7.  Dans la boîte de dialogue **Définir le partage de fichiers** , effectuez l’une des opérations suivantes :
    
      - Pour utiliser un partage de fichiers existant, cliquez sur **Utiliser un partage de fichiers précédemment défini** , sélectionnez un partage de fichiers dans la liste, puis cliquez sur **Suivant** .
    
      - Pour créer un partage de fichiers, cliquez sur **Définir un nouveau partage de fichiers** , tapez le nom de domaine complet de l’emplacement du partage de fichiers dans **Nom de domaine complet du serveur de fichiers** , tapez le nom du partage dans **Partage de fichiers** , puis cliquez sur **Suivant** .
    
    > [!IMPORTANT]  
    > Le partage de fichiers que vous spécifiez ou créez à cette étape doit exister ou être créé avant de publier la topologie.<br />
    Le partage de fichiers attribué à un directeur n’est pas utilisé, si bien que vous pouvez attribuer le partage de fichiers de n’importe quel pool dans l’entreprise.

8.  Dans la boîte de dialogue **Spécifier l’URL des services web** , dans **URL de base externe** , spécifiez le nom de domaine complet des directeurs, puis cliquez sur **Terminer** .
    
    > [!IMPORTANT]  
    > Le nom doit pouvoir être résolu à partir des serveurs DNS Internet et doit pointer vers l’adresse IP publique du proxy inverse. Celui-ci écoute les demandes HTTP/HTTPS envoyées à cette URL et les redirige via proxy au répertoire virtuel des services web externes sur ce pool directeur.    
    > [!WARNING]  
    > Si vous installez plus d’un pool de serveurs frontaux ou serveur frontal, le nom de domaine complet (FQDN) des services web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services web externes d’un serveur frontal en tant que <strong>pool01.contoso.com</strong>, vous ne pouvez pas utiliser ce nom <strong>pool01.contoso.com</strong> pour un autre pool de serveurs frontaux ou serveur frontal. Si vous déployez aussi des directeurs, le nom de domaine complet des services web externes défini pour un directeur ou un pool de directeurs doit être différent de tout autre directeur ou pool de directeurs et de tout pool de serveurs frontaux ou serveur frontal existant. Si vous choisissez de remplacer le nom des services web internes par un nom de domaine complet personnalisé, chaque nom de domaine complet doit être distinct des autres noms de pool de serveurs frontaux, directeur ou pool de directeurs.

9.  Publiez la topologie.

