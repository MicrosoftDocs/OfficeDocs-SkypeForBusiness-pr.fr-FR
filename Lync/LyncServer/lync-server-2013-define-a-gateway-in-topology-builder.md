---
title: 'Lync Server 2013 : Définition d’une passerelle dans le générateur de topologie'
TOCTitle: Définition d’une passerelle dans le générateur de topologie
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425945(v=OCS.15)
ms:contentKeyID: 49297068
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition d’une passerelle dans le générateur de topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-04_

Suivez ces étapes afin d’utiliser le Générateur de topologie pour définir un *homologue* auquel vous pouvez associer un serveur de médiation, ce qui permet d’offrir une connectivité RTC aux utilisateurs ayant accès à Voix Entreprise. L’homologue du serveur de médiation peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP, Internet Telephony Service Provider) auquel vous vous connectez en configurant une jonction SIP.

> [!NOTE]  
> Dans cette rubrique, nous partons du principe que vous avez configuré au moins un pool de serveurs frontaux ou serveur Standard Edition interne dans au moins un site central avec un serveur de médiation colocalisé ou autonome, comme indiqué dans <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013</a> et <a href="lync-server-2013-publish-the-topology.md">Publication de la topologie dans Lync Server 2013</a> dans la documentation de déploiement. Dans cette rubrique, nous partons également du principe que vous avez vérifié que votre infrastructure respecte les conditions préalables décrites dans <a href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Configuration logicielle requise pour Entreprise Voix dans Lync Server 2013</a> et <a href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Conditions prérequises de configuration et de sécurité pour Voix Entreprise dans Lync Server 2013</a>.

## Pour définir un homologue pour le serveur de médiation

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Sous Lync Server 2013, votre nom de site, Composants partagés, cliquez avec le bouton droit sur le nœud **Passerelles RTC** , puis cliquez sur **Nouvelle passerelle IP/RTC** .
    
    ![Générateur de topologie Lync Server 2013](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "Générateur de topologie Lync Server 2013")

3.  Dans **Définir une nouvelle passerelle IP/RTC** , tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant** .
    
    ![Passerelle IP/RTC](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "Passerelle IP/RTC")
    
    > [!NOTE]  
    > Si vous spécifiez Transport Layer Security (TLS) comme type de transport, vous devez spécifier le nom de domaine complet (FQDN) au lieu de l’adresse IP de l’homologue du serveur de médiation.

4.  Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle RTC, puis cliquez sur **Suivant** .
    
    ![Adresse IP](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "Adresse IP")

5.  Définissez une *jonction racine* pour la passerelle RTC. Une jonction est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.
    
    {Nom de domaine complet (FQDN) du serveur de médiation, port d’écoute (TLS ou TCP) du serveur de médiation : IP et FQDN de passerelle, port d’écoute de passerelle}
    
      - Lors de la définition d’une passerelle RTC dans le Générateur de topologie, vous devez définir une jonction racine pour ajouter correctement la passerelle RTC à votre topologie.
    
      - Vous ne pouvez pas supprimer la jonction racine tant que la passerelle RTC associée n’est pas supprimée.
    
    ![Définition d’une passerelle : jonction principale](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "Définition d’une passerelle : jonction principale")

6.  Sous **Port d’écoute pour la passerelle IP/RTC** , tapez le port d’écoute que la passerelle, l’autocommutateur privé (PBX) ou le contrôleur SBC utilisera pour les messages SIP provenant du serveur de médiation associé à la jonction racine de la passerelle RTC. (Par défaut, les ports sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security) sur une passerelle RTC, un autocommutateur privé (PBX) ou un contrôleur SBC. Sur un Survivable Branch Appliance sur le site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)

7.  Sous **Protocole de transport SIP** , cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK** .
    
    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue vers le serveur de médiation qui peut utiliser TLS.

8.  Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer à la jonction racine de cette passerelle RTC.

9.  Sous **Port du serveur de médiation associé** , tapez le port d’écoute que le serveur de médiation doit utiliser pour les messages SIP provenant de la passerelle.
    
    > [!NOTE]  
    > Avec la prise en charge des jonctions multiples dansLync Server 2013, vous pouvez définir plusieurs ports de signalisation SIP sur le serveur de médiation à des fins de communication avec plusieurs passerelles RTC. Lors de la définition d’une jonction, le numéro de <strong>port de serveur de médiation associé</strong> doit être compris dans la plage des ports d’écoute pour le protocole concerné autorisé par le serveur de médiation. Cette plage de ports est définie sous Lync Server 2013 et Pools de médiation. Cliquez avec le bouton droit sur le pool de serveurs de médiation souhaité, puis sélectionnez <strong>Modifier les propriétés</strong>. Spécifiez la plage de ports dans le champ <strong>Ports d’écoute</strong> .

10. Cliquez sur **Terminer** .

> [!IMPORTANT]  
> Avant de terminer cette étape, assurez-vous que l’homologue que vous avez défini est en cours d’exécution et qu’il utilise le nom de domaine complet ou l’adresse IP que vous avez spécifié(e).

Ensuite, pour ajouter l’homologue à la topologie, suivez les procédures décrites dans la section [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) de la documentation de déploiement. Vous devez publier votre topologie chaque fois que vous utilisez le Générateur de topologie pour créer ou modifier votre topologie afin que les données puissent être utilisées pour installer les fichiers des serveurs qui exécutent Lync Server.

## Voir aussi

#### Tâches

[Modification d’une jonction dans le générateur de topologie dans Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)

