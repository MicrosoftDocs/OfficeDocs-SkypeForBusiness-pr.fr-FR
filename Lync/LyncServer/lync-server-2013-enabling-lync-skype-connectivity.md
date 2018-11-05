---
title: 'Lync Server 2013 : activation de la connectivité Lync-Skype'
TOCTitle: Activation de la connectivité Lync-Skype
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn440170(v=OCS.15)
ms:contentKeyID: 59602870
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation de la connectivité Lync-Skype dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Une fois la demande d'approvisionnement transmise, vous pouvez vous concentrer sur l'environnement Lync Server et les tâches d'administration nécessaires à la configuration de la connectivité Lync-Skype. Cette section suppose que l'administrateur Lync Server a déployé Lync Server et configuré l'accès externe. Pour plus d'informations sur la configuration de l'accès externe pour Lync Server, voir [Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) et [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Pour préparer l'environnement Lync Server pour la connectivité Lync-Skype, l'administrateur Lync Server doit effectuer les trois tâches suivantes :

## 1\. Configurer la fédération et la connectivité PIC

La fédération est requise pour permettre aux utilisateurs Skype de communiquer avec les utilisateurs Lync dans votre organisation. La connectivité PIC (Public IM Connectivity) est une classe de fédération. Elle doit être configurée pour permettre à vos utilisateurs Lync de communiquer avec les utilisateurs Skype. La fédération et la connectivité PIC sont configurées à l'aide du panneau de configuration Lync Server (affiché ci-dessous).

![Affichage de PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Affichage de PIC")

> [!IMPORTANT]  
> La fédération PIC n'est plus prise en charge par Live Communication Server 2005 SP1 ou Office Communications Server 2007. Les plateformes prises en charge pour la fédération PIC incluent Lync Server 2013, Lync Server 2010 et Office Communications Server 2007 R2.

## 2\. Configurer au moins une stratégie pour la prise en charge de l'accès des utilisateurs fédérés

À l'aide du panneau de configuration Lync Server, l'administrateur doit configurer une ou plusieurs stratégies d'accès des utilisateurs externes pour contrôler la possibilité pour les utilisateurs Skype de collaborer avec les utilisateurs Lync Server internes.

![Stratégies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Stratégies")

## 3\. Configurer le paramètre de fournisseur PIC Skype pour Lync

À l'aide de Lync Server Management Shell, l'administrateur doit configurer la stratégie de client Lync pour afficher Skype comme fournisseur PIC supplémentaire.

> [!NOTE]  
> Les utilisateurs du service PIC ne peuvent pas participer à des sessions de messagerie instantanée ou des conférences audio ou vidéo dans votre organisation tant que vous n’avez pas configuré au moins une stratégie (étape 2 de cette procédure) pour prendre en charge la connectivité PIC.

1.  Pour configurer la fédération et la connectivité PIC, voir « Activation ou désactivation de la fédération et de la connectivité PIC (Public IM Connectivity) » à l'adresse [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).

2.  Pour configurer au moins une stratégie pour prendre en charge l'accès des utilisateurs fédérés, voir « Configuration des stratégies de contrôle d'accès des utilisateurs publics » à l'adresse [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).

**Pour modifier un fournisseur PIC Messenger et le configurer pour Skype**

1.  À partir d'un serveur frontal Lync Server, ouvrez Lync Server Management Shell.

2.  Exécutez les deux commandes suivantes :
    
    `Remove-CsPublicProvider -Identity Messenger`
    
    `New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png" -VerificationLevel 2 -Enabled 1`

3.  À partir d’un client Lync, vous pouvez désormais sélectionner Skype en tant que fournisseur PIC, et ajouter un client Skype en spécifiant son compte Microsoft. De plus, un utilisateur Skype qui a effectué la fusion et qui est connecté à partir de son compte Microsoft peut envoyer une demande de contact aux utilisateurs Lync. Pour plus d’informations sur les comptes Microsoft, voir [Qu'est-ce qu’un compte Microsoft ?](https://support.skype.com/fr/faq/fa12059/what-is-a-microsoft-account). Pour plus d’informations concernant l’ajout de clients à Lync, voir [Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Ajouter un contact Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Ajouter un contact Skype")

4.  Pour plus d'informations sur la modification des fournisseurs hébergés, voir « Création ou modification de fournisseurs fédérés SIP hébergés » à l'adresse [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).

Cette procédure termine les tâches d'administration qui doivent être effectuées sur le serveur. Vous pouvez à présent utiliser la connectivité Lync-Skype.

