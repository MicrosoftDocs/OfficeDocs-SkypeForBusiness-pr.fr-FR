---
title: "Lync Server 2013 : Déf. d’autres jonctions dans le Gestionnaire de topologies"
TOCTitle: Définition d’autres jonctions dans le Gestionnaire de topologies
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49891583
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition d’autres jonctions dans le Gestionnaire de topologies dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-04_

Procédez comme suit afin d’utiliser le Générateur de topologie pour définir un tronçon supplémentaire auquel vous pouvez associer un *homologue* avec un serveur de médiation. Un homologue fournit aux utilisateurs autorisés pour Voix Entreprise une connectivité au réseau téléphonique commuté (RTC). L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur de session en périphérie (SBC) pour un fournisseur de services de téléphonie Internet (Internet telephony service provider, ITSP). Le tronçon définit cette connexion entre le serveur de médiation et l’homologue. Les tronçons multiples peuvent être définis par le serveur de médiation. Un serveur de médiation peut être associé à plusieurs homologues.

Un tronçon est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple :

{Nom de domaine complet (FQDN) du serveur de médiation, port d’écoute (TLS ou TCP) du serveur de médiation : IP et FQDN de passerelle, port d’écoute de passerelle}

> [!NOTE]  
> Cette rubrique part du principe que vous avez installé une passerelle RTC et un tronçon racine avec au moins un serveur de médiation colocalisé ou autonome, ou un pool, tel que décrit dans la section <a href="lync-server-2013-define-a-gateway-in-topology-builder.md">Définition d’une passerelle dans le générateur de topologie dans Lync Server 2013</a> (contenu éventuellement en anglais) de la documentation relative au déploiement.

> [!NOTE]  
> Cette rubrique part du principe que vous avez installé au moins un pool de serveurs frontaux ou serveur Standard Edition dans au moins un site central, tel que décrit dans les sections <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013</a> et <a href="lync-server-2013-publish-the-topology.md">Publication de la topologie dans Lync Server 2013</a> de la documentation relative au déploiement.

## Pour définir un tronçon supplémentaire entre un serveur de médiation et un homologue de passerelle

1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Sous Lync Server 2013, votre nom de site, **Composants partagés** , cliquez avec le bouton droit sur le nœud **Tronçons** , puis cliquez sur **Nouveau tronçon** .
    
    ![Écran de la structure de fichier du Générateur de topologie Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Écran de la structure de fichier du Générateur de topologie Lync Server")

3.  Dans **Définir un nouveau tronçon** , spécifiez un nom convivial pour identifier le tronçon de manière unique. Deux tronçons ne peuvent pas avoir le même nom.
    
    > [!NOTE]  
    > Si vous spécifiez Transport Layer Security (TLS) comme type de transport, vous devez spécifier le nom de domaine complet (FQDN) au lieu de l’adresse IP de l’homologue du serveur de médiation.

4.  Sous **Passerelle RTC associée** , sélectionnez l’homologue de passerelle RTC à associer à ce tronçon.
    
    ![Paramètres des propriétés pour la passerelle PSTN homologue pour la jonction](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Paramètres des propriétés pour la passerelle PSTN homologue pour la jonction")

5.  Sous **Port d’écoute pour la passerelle RTC** , tapez le port d’écoute dans lequel l’homologue (passerelle RTC, IP-PBX, ou SBC) recevra les messages SIP du serveur de médiation qui doit être associé à ce tronçon. Les ports homologues par défaut sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security). Les ports de l’Survivable Branch Appliance sont 5081 pour TCP et 5082 pour TLS.

6.  Sous **Protocole de transport SIP** , cliquez sur le type de transport utilisé par l’homologue.
    
    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue vers le serveur de médiation qui peut utiliser TLS.

7.  Sous **Serveur de médiation associé** , sélectionnez le pool du serveur de médiation à associer avec le tronçon racine de cet homologue

8.  Sous **Port du serveur de médiation associé** , tapez le port d’écoute dans lequel le serveur de médiation recevra les messages SIP de l’homologue.
    
    > [!NOTE]  
    > Avec la prise en charge de plusieurs tronçons dans Lync Server 2013, deux tronçons ayant des noms différents ne peuvent pas être configurés avec les mêmes <strong>port de serveur de médiation associé</strong> et <strong>port d’écoute pour passerelle IP/RTC</strong>    
    > [!NOTE]  
    > Avec la prise en charge de plusieurs tronçons dans Lync Server 2013, plusieurs ports de signalisation SIP peuvent être définis sur le serveur de médiation pour la communication avec plusieurs homologues. Lors de la définition d’un tronçon, le numéro du <strong>port de serveur de médiation associé</strong> doit être compris dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation. Cette plage de ports est définie pour Lync Server 2013 et les pools de serveurs de médiation. Cliquez avec le bouton droit sur le pool de serveurs de médiation approprié, puis sélectionnez <strong>Modifier les propriétés</strong> . Spécifiez la plage de ports dans le champ <strong>Ports d’écoute</strong> .

9.  Cliquez sur **OK** .

## Voir aussi

#### Tâches

[Modification d’une jonction dans le générateur de topologie dans Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)

