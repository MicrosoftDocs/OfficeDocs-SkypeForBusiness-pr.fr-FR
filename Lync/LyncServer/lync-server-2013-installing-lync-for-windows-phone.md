---
title: 'Lync Server 2013 : installation de Lync pour Windows Phone'
description: 'Lync Server 2013 : installation de Lync pour Windows Phone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573980"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Installation de Lync pour Windows Phone dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-03_

Lync 2013 pour Windows Phone est une application installable par l’utilisateur et disponible sur le site Marketplace Windows Phone.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Installation de Lync pour Windows Mobile

Vous pouvez demander à vos utilisateurs d’installer Lync 2013 pour Windows Phone sur leurs appareils en les dirigeant vers Windows Phone Marketplace à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=231901> .

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Si vous utilisez un enregistrement SRV DNS pour publier des services Web Exchange

Pour activer l’intégration d’Exchange pour les clients Lync, certaines organisations publient l’URL des services Web Exchange à l’aide d’un enregistrement SRV DNS. Le document « Understanding and Troubleshooting Exchange Integration », disponible dans le centre de téléchargement Microsoft à l’adresse [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) , décrit les scénarios dans lesquels cela peut s’avérer nécessaire. Toutefois, l’intégration d’Exchange pour les utilisateurs de Windows Phone ne fonctionnera pas dans ce scénario, car la plateforme Windows Phone ne prend pas en charge les recherches SRV. Vous devrez indiquer aux utilisateurs Windows Phone de spécifier l’URL des services Web Exchange au lieu de permettre au téléphone de détecter automatiquement le serveur.

Demandez à vos utilisateurs de configurer les paramètres Lync sur leurs téléphones Windows comme suit :

1.  Dans Windows Phone, dans les paramètres de Lync, sélectionnez l’écran **Exchange** .

2.  Déplacez **le serveur de détection automatique** sur **désactivé**.

3.  Appuyez sur le champ vide et entrez le nom de domaine complet (FQDN) ou l’URL des services Web Exchange.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez spécifier le nom de domaine complet (FQDN) ou l’URL complète de votre serveur de services Web Exchange. Si vous spécifiez le nom de domaine complet, le protocole (https://) et le chemin d’accès des services Web Exchange (/EWS/Exchange.asmx) sont automatiquement ajoutés. Si votre chemin d’accès aux services Web Exchange est différent, vous pouvez spécifier l’URL complète.

    
    </div>

4.  Fermer l’écran.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Vérification de l’installation du client mobile

Après avoir configuré le client et s’être connecté, utilisez les tests suivants pour vérifier que votre installation de Lync 2013 fonctionne correctement sur votre appareil mobile.

**Rechercher un contact dans l’annuaire d’entreprise**

1.  Dans la liste Contacts, tapez sur **Rechercher** en bas.

2.  Recherchez un contact qui n’existe que dans la liste d’adresses globale.

3.  Vérifiez que le nom du contact figure dans les résultats de la recherche.

**Tester la messagerie instantanée et la présence**

1.  Dans la liste Contacts, tapez sur un contact.

2.  Dans la carte de visite, tapez sur l’icône **IM**.

3.  Vérifiez qu’une fenêtre de messagerie instantanée apparaît et que vous pouvez taper et envoyer un message instantané.

**Tester la conférence rendez-vous**

1.  Dans Outlook, planifiez une réunion Lync.

2.  Sur l’appareil mobile, ouvrez l’invitation à la réunion.

3.  Cliquez sur le lien dans la réunion afin de la rejoindre.

4.  Répondez à l’appel du service de conférence et vérifiez que vous êtes connecté au système audio de la réunion.

**Tester les notifications de type push**

1.  Sur l’appareil mobile de l’utilisateur A, connectez-vous à Lync avec le compte de l’utilisateur A.

2.  Ouvrez une autre application sur l’appareil mobile.

3.  Sur un autre client, connectez-vous à Lync avec le compte de l’utilisateur B.

4.  Envoyez un message instantané de l’utilisateur B à l’utilisateur A.

5.  Vérifiez que la notification de messagerie instantanée s’affiche sur l’appareil mobile de l’utilisateur A.

</div>

</div>

<span> </span>

</div>

</div>

</div>

