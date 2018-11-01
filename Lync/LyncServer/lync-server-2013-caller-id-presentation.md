---
title: 'Lync Server 2013 : Présentation de l’ID d’appelant'
TOCTitle: Présentation de l’ID d’appelant
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204980(v=OCS.15)
ms:contentKeyID: 49297506
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Présentation de l’ID d’appelant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Avec Lync Server 2010, le numéro de téléphone du destinataire (numéro de téléphone appelé) peut être converti du format E.164 au format de numérotation local requis par l’*homologue de jonction* (passerelle associée, système PBX ou jonction SIP). Pour ce faire, vous devez définir une ou plusieurs règles de conversion pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.

Lync Server 2013 introduit la possibilité de convertir aussi le numéro de téléphone de l’appelant (c’est-à-dire, le numéro de téléphone de la personne à l’origine de l’appel) du format E.164 au format de numérotation local qui est requis par l’homologue de jonction. Par exemple, vous pouvez écrire une règle de conversion pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.

**Pour configurer l’identification de l’appelant à l’aide du Panneau de configuration Lync Server**

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales** , puis sur **Configuration de la jonction** .

4.  Dans la page **Configuration de la jonction** , double-cliquez sur une jonction existante (par exemple, la jonction **Global** ) pour afficher la boîte de dialogue **Modifier la configuration de la jonction** .

5.  Pour configurer la présentation de l’identification de l’appelant :
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de conversion disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner** . Dans **Règles de conversion du numéro d’appel** , cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK** .
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle** . Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails** . Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, cliquez sur le nom de la règle, sur **Copier** , puis sur **Coller** . Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer** .
    
    > [!WARNING]  
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.
