---
title: Configuration du serveur de médiation
TOCTitle: Configuration du serveur de médiation
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204913(v=OCS.15)
ms:contentKeyID: 49297245
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du serveur de médiation

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette procédure détaille les étapes pour configurer le pool Lync Server 2013 pour qu’il utilise le serveur de médiation Lync Server 2013 à la place du serveur de médiation Office Communications Server 2007 R2 hérité.

Pour réussir à publier, activer ou désactiver une topologie quand vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Il est également possible de déléguer les droits et autorisations d’administrateur appropriés pour ajouter des rôles serveur. Pour plus d’informations, reportez-vous à4 Déléguer des autorisations de configuration dans la documentation de déploiement consacrée aux serveurs Standard Edition ou Enterprise Edition. Pour toutes les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est nécessaire.

> [!NOTE]  
> Pour obtenir les dernières informations sur la détection des passerelles RTC, des systèmes et des services de jonction SIP qualifiés fonctionnant avec Lync Server 2013, reportez-vous à « Microsoft Unified Communications Open Interoperability Program » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</a>.

## Pour configurer le serveur de médiation à l’aide du générateur de topologie

1.  Ouvrez une topologie existante à partir du générateur de topologie.

2.  Dans le volet gauche, accédez à **Passerelles RTC** .

3.  Cliquez avec le bouton droit sur **Passerelles RTC** , puis cliquez sur **Nouvelle passerelle IP/RTC** .

4.  Complétez la page **Définir une nouvelle passerelle IP/RTC** à l’aide des informations suivantes :
    
      - Entrez le nom de domaine complet ou l’adresse IP de la passerelle. Le nom de domaine complet de la passerelle est nécessaire si celle-ci utilise le protocole TLS.
    
      - Acceptez la valeur **Port d’écoute de la passerelle IP/RTC** par défaut ou entrez le nouveau port d’écoute s’il a été modifié.
    
      - Définissez la valeur **Protocole de transport SIP** .

5.  Dans le volet gauche, accédez au **Pool frontal Enterprise Edition** ou au **Serveur Standard Edition** .

6.  Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés** .

7.  Sous **Serveur de médiation** , définissez les **Ports d’écoute** .

8.  Ensuite, associez la nouvelle passerelle RTC créée en la sélectionnant, puis en cliquant sur **Ajouter** .

9.  Dans le **Générateur de topologie** , sélectionnez le nœud de niveau supérieur **Lync Server** .

10. Dans le menu **Action** , sélectionnez **Publier la topologie** , puis cliquez sur **Suivant** .

11. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.

> [!NOTE]  
> Il est important d’accomplir la rubrique suivante, <a href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Modification des itinéraires de communications vocales pour l’utilisation du nouveau serveur de médiation Lync Server 2013</a> pour garantir que les itinéraires des communications vocales pointent vers le serveur de médiation approprié.
