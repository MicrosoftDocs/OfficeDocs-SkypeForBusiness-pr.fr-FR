---
title: Installation de Lync pour Windows Phone
TOCTitle: Installation de Lync pour Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690996(v=OCS.15)
ms:contentKeyID: 53095515
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation de Lync pour Windows Phone

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync 2013 pour Windows Phone est une application installable par l’utilisateur et disponible sur le site Marketplace Windows Phone.

## Installation de Lync pour Windows Mobile

Vous pouvez demander à vos utilisateurs d’installer Lync 2013 pour Windows Phone sur leur appareil en les dirigeant vers le site Marketplace Windows Phone à l’adresse <http://go.microsoft.com/fwlink/?linkid=231901>.

## Si vous utilisez un enregistrement SRV DNS pour publier des services Web Exchange

Pour activer l'intégration Exchange pour les clients Lync, certaines organisations publient l'URL des services Web Exchange en utilisant un enregistrement SRV DNS. Le document « Comprendre et dépanner l'intégration de Microsoft Exchange Server  », disponible dans le Centre de téléchargement Microsoft à l'adresse [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), décrit les scénarios dans lesquels cela peut s'avérer nécessaire. Cependant, l'intégration d'Exchange pour les utilisateurs de Windows Phone ne fonctionne pas dans ce scénario, car la plateforme Windows Phone ne prend pas en charge les recherches SRV. Vous devez indiquer aux utilisateurs de Windows Phone de spécifier l'URL des services Web Exchange au lieu de laisser le téléphone détecter automatiquement le serveur.

Indiquez aux utilisateurs de configurer les paramètres Lync sur leurs téléphones Windows Phone comme suit :

1.  Dans Windows Phone, dans les paramètres Lync, sélectionnez l'écran **Exchange**.

2.  Définissez l'option **Détecter automatiquement le serveur** sur **Inactif**.

3.  Appuyez sur le champ vide et entrez le nom de domaine complet (FQDN) ou l'URL pour les services Web Exchange.
    
    > [!NOTE]  
    > Vouis pouvez spécifier le nom de domaine complet (FQDN) ou l'URL complète de votre serveur des services Web Exchange. Si vous spécifiez le FQDN, le protocole (https://) et le chemin d'accès des services Web Exchange (/ews/exchange.asmx) sont ajoutés automatiquement. Si votre chemin d'accès des services Web Exchange est différent, vous pouvez spécifier l'URL complète.

4.  Fermez l'écran.

## Vérification de l’installation du client mobile

Après avoir configuré le client et ouvert une session, procédez aux tests suivants pour vérifier que votre installation de Lync 2013 fonctionne correctement sur votre appareil mobile.

**Rechercher un contact dans l’annuaire d’entreprise**

1.  Dans la liste Contacts, tapez sur **Rechercher** en bas.

2.  Recherchez un contact qui n’existe que dans la liste d’adresses globale.

3.  Vérifiez que le nom du contact figure dans les résultats de la recherche.

**Tester la messagerie instantanée et la présence**

1.  Dans la liste Contacts, tapez sur un contact.

2.  Dans la carte du contact, tapez sur l’icône **IM**.

3.  Vérifiez qu’une fenêtre de messagerie instantanée apparaît et que vous pouvez taper et envoyer un message instantané.

**Tester la conférence rendez-vous**

1.  Dans Outlook, planifiez une réunion Lync.

2.  Sur l’appareil mobile, ouvrez l’invitation à la réunion.

3.  Cliquez sur le lien dans la réunion afin de la rejoindre.

4.  Répondez à l’appel du service de conférence et vérifiez que vous êtes connecté au système audio de la réunion.

**Tester les notifications push**

1.  Sur l’appareil mobile de l’utilisateur A, connectez-vous à Lync avec le compte de l’utilisateur A.

2.  Ouvrez une autre application sur l’appareil mobile.

3.  Sur un autre client, connectez-vous à Lync avec le compte de l’utilisateur B.

4.  Envoyez un message instantané de l’utilisateur B à l’utilisateur A.

5.  Vérifiez que la notification de messagerie instantanée s’affiche sur l’appareil mobile de l’utilisateur A.

