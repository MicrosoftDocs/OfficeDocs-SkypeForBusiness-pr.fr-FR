---
title: 'Lync Server 2013 : installation de Lync pour Windows Phone'
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
ms.openlocfilehash: 349a4b2609f3b810d0aa64c9e71786f309f21918
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="0c795-102">Installation de Lync pour Windows Phone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c795-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c795-103">_**Dernière modification de la rubrique :** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="0c795-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="0c795-104">Lync 2013 pour Windows Phone est une application installable par l’utilisateur et disponible sur le site Marketplace Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="0c795-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="0c795-105">Installation de Lync pour Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="0c795-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="0c795-106">Vous pouvez demander à vos utilisateurs d’installer Lync 2013 pour Windows Phone sur leurs appareils en les dirigeant vers Windows Phone Marketplace à l' <http://go.microsoft.com/fwlink/p/?linkid=231901>adresse.</span><span class="sxs-lookup"><span data-stu-id="0c795-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="0c795-107">Si vous utilisez un enregistrement SRV DNS pour publier des services Web Exchange</span><span class="sxs-lookup"><span data-stu-id="0c795-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="0c795-108">Pour activer l’intégration d’Exchange pour les clients Lync, certaines organisations publient l’URL des services Web Exchange à l’aide d’un enregistrement SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="0c795-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="0c795-109">Le document « Understanding and Troubleshooting Exchange Integration », disponible dans le centre [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)de téléchargement Microsoft à l’adresse, décrit les scénarios dans lesquels cela peut s’avérer nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0c795-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="0c795-110">Toutefois, l’intégration d’Exchange pour les utilisateurs de Windows Phone ne fonctionnera pas dans ce scénario, car la plateforme Windows Phone ne prend pas en charge les recherches SRV.</span><span class="sxs-lookup"><span data-stu-id="0c795-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="0c795-111">Vous devrez indiquer aux utilisateurs Windows Phone de spécifier l’URL des services Web Exchange au lieu de permettre au téléphone de détecter automatiquement le serveur.</span><span class="sxs-lookup"><span data-stu-id="0c795-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="0c795-112">Demandez à vos utilisateurs de configurer les paramètres Lync sur leurs téléphones Windows comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c795-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="0c795-113">Dans Windows Phone, dans les paramètres de Lync, sélectionnez l’écran **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="0c795-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="0c795-114">Déplacez **le serveur de détection automatique** sur **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="0c795-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="0c795-115">Appuyez sur le champ vide et entrez le nom de domaine complet (FQDN) ou l’URL des services Web Exchange.</span><span class="sxs-lookup"><span data-stu-id="0c795-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c795-116">Vous pouvez spécifier le nom de domaine complet (FQDN) ou l’URL complète de votre serveur de services Web Exchange.</span><span class="sxs-lookup"><span data-stu-id="0c795-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="0c795-117">Si vous spécifiez le nom de domaine complet, le protocole (https://) et le chemin d’accès des services Web Exchange (/EWS/Exchange.asmx) sont automatiquement ajoutés.</span><span class="sxs-lookup"><span data-stu-id="0c795-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="0c795-118">Si votre chemin d’accès aux services Web Exchange est différent, vous pouvez spécifier l’URL complète.</span><span class="sxs-lookup"><span data-stu-id="0c795-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="0c795-119">Fermer l’écran.</span><span class="sxs-lookup"><span data-stu-id="0c795-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="0c795-120">Vérification de l’installation du client mobile</span><span class="sxs-lookup"><span data-stu-id="0c795-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="0c795-121">Après avoir configuré le client et s’être connecté, utilisez les tests suivants pour vérifier que votre installation de Lync 2013 fonctionne correctement sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="0c795-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="0c795-122">**Rechercher un contact dans l’annuaire d’entreprise**</span><span class="sxs-lookup"><span data-stu-id="0c795-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="0c795-123">Dans la liste Contacts, tapez sur **Rechercher** en bas.</span><span class="sxs-lookup"><span data-stu-id="0c795-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="0c795-124">Recherchez un contact qui n’existe que dans la liste d’adresses globale.</span><span class="sxs-lookup"><span data-stu-id="0c795-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="0c795-125">Vérifiez que le nom du contact figure dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="0c795-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="0c795-126">**Tester la messagerie instantanée et la présence**</span><span class="sxs-lookup"><span data-stu-id="0c795-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="0c795-127">Dans la liste Contacts, tapez sur un contact.</span><span class="sxs-lookup"><span data-stu-id="0c795-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="0c795-128">Dans la carte de visite, tapez sur l’icône **IM**.</span><span class="sxs-lookup"><span data-stu-id="0c795-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="0c795-129">Vérifiez qu’une fenêtre de messagerie instantanée apparaît et que vous pouvez taper et envoyer un message instantané.</span><span class="sxs-lookup"><span data-stu-id="0c795-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="0c795-130">**Tester la conférence rendez-vous**</span><span class="sxs-lookup"><span data-stu-id="0c795-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="0c795-131">Dans Outlook, planifiez une réunion Lync.</span><span class="sxs-lookup"><span data-stu-id="0c795-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="0c795-132">Sur l’appareil mobile, ouvrez l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="0c795-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="0c795-133">Cliquez sur le lien dans la réunion afin de la rejoindre.</span><span class="sxs-lookup"><span data-stu-id="0c795-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="0c795-134">Répondez à l’appel du service de conférence et vérifiez que vous êtes connecté au système audio de la réunion.</span><span class="sxs-lookup"><span data-stu-id="0c795-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="0c795-135">**Tester les notifications de type push**</span><span class="sxs-lookup"><span data-stu-id="0c795-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="0c795-136">Sur l’appareil mobile de l’utilisateur A, connectez-vous à Lync avec le compte de l’utilisateur A.</span><span class="sxs-lookup"><span data-stu-id="0c795-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="0c795-137">Ouvrez une autre application sur l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="0c795-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="0c795-138">Sur un autre client, connectez-vous à Lync avec le compte de l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="0c795-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="0c795-139">Envoyez un message instantané de l’utilisateur B à l’utilisateur A.</span><span class="sxs-lookup"><span data-stu-id="0c795-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="0c795-140">Vérifiez que la notification de messagerie instantanée s’affiche sur l’appareil mobile de l’utilisateur A.</span><span class="sxs-lookup"><span data-stu-id="0c795-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

