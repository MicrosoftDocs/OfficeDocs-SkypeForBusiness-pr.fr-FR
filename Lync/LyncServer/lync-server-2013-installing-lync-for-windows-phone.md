---
title: 'Lync Server 2013: installation de Lync pour Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeb8f43ea4f4db15a9a057bd0d7b24c55d858cb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Installation de Lync pour Windows Phone dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-03_

Lync 2013 pour Windows Phone est une application qui est disponible sur Windows Phone Marketplace.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Installation de Lync pour Windows Mobile

Vous pouvez indiquer à vos utilisateurs d’installer Lync 2013 pour Windows Phone sur leurs appareils en les redirigeant vers Windows Phone Marketplace <http://go.microsoft.com/fwlink/p/?linkid=231901>à l’adresse.

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Si vous utilisez un enregistrement SRV DNS pour publier des services Web Exchange

Pour activer l’intégration Exchange pour les clients Lync, certaines organisations publient l’URL du service Web Exchange à l’aide d’un enregistrement SRV DNS. Le document «comprendre et résoudre les problèmes d’intégration d’Exchange», disponible dans le [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)Centre de téléchargement Microsoft à, décrit les scénarios dans lesquels cela peut être nécessaire. Toutefois, l’intégration Exchange pour les utilisateurs Windows Phone ne fonctionnera pas dans ce scénario, car la plateforme Windows Phone ne prend pas en charge les recherches SRV. Vous devez indiquer aux utilisateurs Windows Phone de spécifier l’URL du service Web Exchange au lieu de laisser le téléphone détecter automatiquement le serveur.

Demandez à vos utilisateurs de configurer les paramètres Lync sur leurs téléphones Windows comme suit:

1.  Dans les paramètres de Lync pour Windows Phone, sélectionnez l’écran **Exchange** .

2.  Pour **Désactiver**l’option **détecter automatiquement le serveur,**

3.  Appuyez sur le champ vide, puis entrez le nom de domaine complet (FQDN) ou l’URL des services Web Exchange.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez spécifier le nom de domaine complet (FQDN) ou l’URL complète de votre serveur de services Web Exchange. Si vous spécifiez le nom de domaine complet, le protocole (https://) et le chemin d’accès aux services Web Exchange (/EWS/Exchange.asmx) sont automatiquement ajoutés. Si votre chemin d’accès aux services Web Exchange est différent, vous pouvez spécifier l’URL complète.

    
    </div>

4.  Fermez l’écran.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Vérification de l’installation du client mobile

Après avoir configuré le client et que vous êtes connecté avec succès, utilisez les tests suivants pour vérifier que votre installation de Lync 2013 fonctionne correctement sur votre appareil mobile.

**Recherche d’un contact dans l’annuaire d’entreprise**

1.  Dans la liste des contacts, appuyez sur **Rechercher** en bas.

2.  Recherchez un contact qui n’existe que dans la liste d’adresses globale.

3.  Vérifiez que le nom du contact figure dans les résultats de la recherche.

**Test de la messagerie instantanée et de la présence**

1.  Dans la liste Contacts, tapez sur un contact.

2.  Sur la carte de visite, appuyez sur l’icône de **messagerie instantanée** .

3.  Vérifiez qu’une fenêtre de messagerie instantanée apparaît et que vous pouvez taper et envoyer un message instantané.

**Test de la conférence rendez-vous**

1.  Dans Outlook, planifiez une réunion Lync.

2.  Sur l’appareil mobile, ouvrez l’invitation à la réunion.

3.  Cliquez sur le lien dans la réunion afin de la rejoindre.

4.  Répondez à l’appel du service de conférence et vérifiez que vous êtes connecté au système audio de la réunion.

**Test des notifications Push**

1.  Sur l’appareil mobile de l’utilisateur, connectez-vous à Lync avec le compte de l’utilisateur.

2.  Ouvrez une autre application sur l’appareil mobile.

3.  Sur un autre client, connectez-vous à Lync avec le compte de l’utilisateur B.

4.  Envoyez un message instantané de l’utilisateur B à l’utilisateur A.

5.  Vérifiez que la notification de messagerie instantanée s’affiche sur l’appareil mobile de l’utilisateur A.

</div>

</div>

<span> </span>

</div>

</div>

</div>

