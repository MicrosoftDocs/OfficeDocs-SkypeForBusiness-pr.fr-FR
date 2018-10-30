---
title: Configurer un nouveau serveur d'applications approuvées dans Lync Server 2013
TOCTitle: Configurer un nouveau serveur d'applications approuvées dans Lync Server 2013
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg617964(v=OCS.15)
ms:contentKeyID: 49298435
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer un nouveau serveur d'applications approuvées dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Une application approuvée est une application basée sur Kit de développement logiciel (SDK) Microsoft Unified Communications Managed API (UCMA) 3.0 Core qui est approuvée par Microsoft Lync Server 2013. Pour plus d’informations sur les applications UCMA, voir la documentation du kit de développement logiciel (SDK) Unified Communications Managed API 3.0 à l’adresse [http://go.microsoft.com/fwlink/?linkid=210320\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=210320%26clcid=0x40c).

Pour plus d’informations sur la configuration de Microsoft Outlook Web Access (OWA) et de Lync Server 2013, voir « Configurer l’intégration d’Outlook Web App et de Lync Server 2010 » dans la documentation de Microsoft Exchange Server 2013.

Pour publier, activer ou désactiver avec succès une topologie lorsque vous ajoutez ou enlevez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine. Il est également possible de déléguer les autorisations et les droits appropriés d’administrateur pour ajouter des rôles serveur. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement. Pour procéder à d’autres modifications de la configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est nécessaire.

## Pour configurer un serveur d’applications approuvées

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

3.  Sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

4.  Dans la boîte de dialogue **Enregistrer la topologie sous**, cliquez sur le fichier Générateur de topologie que vous voulez utiliser, puis sur **Enregistrer**.

5.  Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications approuvées**, puis sur **Nouveau pool d’applications approuvées**.

6.  Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée, sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple, puis cliquez sur **Suivant**.

7.  Dans la page **Sélectionner le tronçon suivant**, dans la liste, sélectionnez le pool de serveurs frontauxLync Server 2013.

8.  Cliquez sur **Terminer**.

9.  Sélectionnez le nœud supérieur **Lync Server 2013** puis, dans le menu **Actions**, cliquez sur **Publier la topologie**.
    
    Le **Pool d’applications approuvées** doit avoir été créé avec succès et associé au pool de serveurs frontaux correct.

