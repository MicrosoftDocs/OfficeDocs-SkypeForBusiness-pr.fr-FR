---
title: 'Lync Server 2013 : Utilisation de la connectivité Lync-Skype en tant qu’utilisateur final'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2bf4584f3332171942f941cc382d22bb6a8db7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-12-27_

Lync-Skype Connectivity permet aux utilisateurs de Skype et aux utilisateurs de Lync de s’ajouter aux contacts, d’échanger des messages instantanés et de passer des appels audio et vidéo. Lorsqu’un utilisateur de Skype ajoute un utilisateur Lync, un utilisateur Skype crée un contact dans Skype contenant l’URI (Uniform Resource Identifier) de l’utilisateur Lync. À l’inverse, quand un utilisateur de Lync ajoute un contact Skype, l’utilisateur de Lync crée un contact dans Lync qui contient le compte Microsoft (MSA) de l’utilisateur Skype, et non le nom d’utilisateur Skype.

**Qu’est-ce qu’un MSA?** Les utilisateurs de Skype doivent se connecter à Skype avec un compte Microsoft (auparavant appelé Windows Live ID) pour communiquer avec des contacts Lync.Un compte Microsoft repose sur la combinaison d’une adresse de messagerie et d’un mot de passe, que vous pouvez également utiliser pour vous connecter à des services tels que la technologie de stockage Microsoft OneDrive, Windows Phone, le service de jeu Microsoft Xbox LIVE Online et la messagerie Microsoft Outlook et client de collaboration (et, auparavant, service de messagerie Web Microsoft Hotmail ou Windows Live Messenger).Si vous utilisez une adresse de messagerie et un mot de passe pour vous connecter à ces services, vous disposez déjà d’un compte Microsoft.Pour plus d’informations sur la création d’un compte Microsoft, reportez-vous [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)à la page de connexion au compte Microsoft à l’adresse. Vous pouvez fusionner votre compte Skype existant avec votre compte Microsoft pour l’authentification unique, dans de nombreuses applications et services. Une fois le compte fusionné, l’utilisateur de Skype peut envoyer une demande de contact aux utilisateurs de Lync.

<div>


> [!IMPORTANT]  
> Pour que les utilisateurs de Lync et Skype puissent communiquer de manière complète, les conditions suivantes doivent être remplies: 
> <UL>
> <LI>
> <P>Les utilisateurs de Skype doivent être connectés à leur client Skype avec un compte Microsoft (MSA).</P>
> <LI>
> <P>Les utilisateurs de Lync doivent être activés pour la connectivité PIC (Public IM Connectivity) par leur administrateur Lync.</P>
> <LI>
> <P>Lorsqu’un utilisateur Skype ajoute un contact Lync, vérifiez que le mot Lync apparaît sous le nom du contact. Cela indique qu’un URI Lync a été trouvé.</P>
> <LI>
> <P>Lorsqu’un utilisateur Skype ajoute un contact Lync et que les résultats de la recherche ne sont pas retournés pour ce domaine Lync, le processus de mise en service de PIC n’est peut-être pas terminé ou le domaine Lync n’a pas encore été configuré.</P>
> <LI>
> <P>En fonction des paramètres de confidentialité de Lync et des utilisateurs Skype, la messagerie instantanée, la vidéo et la présence risquent de ne pas fonctionner tant que les nouveaux contacts ne sont pas acceptés par chaque utilisateur.</P></LI></UL>



</div>

**Pour ajouter un contact Skype à Lync 2013**

1.  Dans Lync, cliquez sur **Ajouter un contact, puis ajoutez un contact qui n’est pas dans ma société**.

2.  Dans la liste des fournisseurs de contacts disponibles, sélectionnez **Skype**.

3.  Dans le champ **adresse de messagerie instantanée** , entrez le compte Microsoft (MSA) de l’utilisateur Skype.

4.  Dans la liste déroulante **Ajouter au groupe de contacts** , sélectionnez le groupe de contacts auquel vous souhaitez ajouter l’utilisateur.

5.  Dans la liste déroulante **définir la relation de confidentialité** , sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.

6.  L’utilisateur s’affiche désormais comme contact dans Lync. Sélectionnez l’utilisateur, cliquez avec le bouton droit sur le nom d’utilisateur, puis cliquez sur **afficher la carte de visite** pour afficher les propriétés de l’utilisateur. Vous pouvez désormais passer un appel audio ou vidéo à l’aide de l’utilisateur Skype que vous venez d’ajouter.

Pour plus d’informations sur la prise en charge des contacts, consultez [Ajouter un contact dans Lync](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).

Lorsque le compte Microsoft d’un utilisateur Skype utilise un nom de domaine personnalisé, tel que <strong>Bob@contoso.com</strong> , un utilisateur de Lync peut ajouter ce compte Microsoft à Lync de deux manières:

1.  Utilisez l’icône **Ajouter un contact** ou

2.  Utilisez le champ **Rechercher une personne ou une salle ou un numéro de** téléphone.

Dans chaque instance, l’utilisateur de Lync doit entrer l’adresse e-mail de l’utilisateur Skype au format suivant: <strong>utilisateur (nom de domaine) @msn. com</strong> .

<div>


> [!IMPORTANT]  
> Cette étape n’est pas requise pour les comptes Microsoft qui utilisent les noms de domaine suivants: <STRONG>@live. com, @hotmail. com ou @outlook. com</STRONG>. Pour plus d’informations sur les noms de domaine personnalisés pris en charge, voir <A href="https://support.microsoft.com/kb/897567">domaines de messagerie instantanée publics pris en charge</A>.



</div>

**Pour ajouter un contact Skype à Lync lors de l’utilisation d’un nom de domaine personnalisé**

1.  Dans Lync, cliquez sur **Ajouter un contact, puis ajoutez un contact qui n’est pas dans ma société**.

2.  Dans la liste des fournisseurs de contacts disponibles, sélectionnez **Skype**.

3.  Dans le champ **adresse de messagerie instantanée** , entrez le compte Microsoft (MSA) de l’utilisateur Skype au format <strong>utilisateur (nom de domaine) @msn. com</strong>. Ainsi, pour l’utilisateur bob@contoso.com, l’entrée <strong>est Bob (contoso. com) @msn.<strong> com.

4.  Dans la zone de liste déroulante **Ajouter au groupe de contacts** , sélectionnez le groupe de contacts auquel vous souhaitez ajouter l’utilisateur.

5.  Dans la zone de liste déroulante **définir la relation de confidentialité** , sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.

6.  Un utilisateur de Lync peut également utiliser le champ **Rechercher une personne ou une salle ou composer un numéro** dans Lync et ajouter une adresse qui ressemble à l' <strong>utilisateur suivant (nom de domaine) @msn. com</strong> . Pour le compte Microsoft bob@contoso.com, l’entrée est <strong>Bob (contoso. com) @msn. com</strong> .

7.  Suivez les étapes 4 et 5 décrites plus haut dans cette procédure pour ajouter le contact à un groupe de contacts et pour sélectionner la relation de confidentialité appropriée.

**Pour ajouter un contact Lync à Skype**

1.  Connectez-vous à Skype. L’utilisateur Skype doit être connecté à son client Skype avec un compte Microsoft (MSA).

2.  Sélectionnez l’icône Ajouter des contacts.

3.  Entrez l’URI SIP de l’utilisateur Lync. Par exemple, bob@contoso.com.

4.  Lorsque Skype trouve la correspondance dans les résultats de recherche, recherchez le mot **Lync** sous le nom de l’utilisateur Lync. Cela indique que Skype a trouvé l’URI SIP du client Lync. Cliquez sur le nom.

5.  Dans le coin supérieur droit de la fenêtre, cliquez sur Ajouter aux contacts.

6.  Le nouveau contact est désormais ajouté à votre liste de contacts, mais un point d’interrogation est affiché au lieu de son icône de statut jusqu’à ce qu’il accepte votre demande. Lorsque votre contact a accepté votre demande, vous pouvez voir quand il est en ligne, lancer des conversations par messagerie instantanée et effectuer des appels audio et vidéo.
    
    <div>
    

    > [!IMPORTANT]  
    > L’administrateur du serveur Lync doit configurer les paramètres de stratégie de l’utilisateur Lync pour autoriser les demandes entrantes. Si ce n’est pas le cas, l’utilisateur de Lync n’aura pas reçu de demandes de contact de l’utilisateur Skype. En fonction de la configuration des paramètres de stratégie de l’utilisateur Lync, la demande d’ajout de l’utilisateur Skype apparaît sous l’onglet <STRONG>nouveau</STRONG> du client Lync. Pour commencer à communiquer avec l’utilisateur Skype, l’utilisateur de Lync doit ajouter l’utilisateur Skype à la liste de favoris ou à une liste de contacts. L’image ci-dessous montre l’emplacement du <STRONG>nouvel</STRONG> onglet dans le client Lync.

    
    </div>

Un utilisateur de Lync doit configurer des alertes Lync pour s’assurer que les demandes envoyées à partir d’un utilisateur Skype apparaissent et qu’ils peuvent être détectés par l’utilisateur de Lync. Pour configurer les alertes Lync, suivez la procédure ci-dessous.

**Pour configurer les alertes Lync**

1.  Dans le client Lync, cliquez sur l’icône **options** .

2.  Sélectionnez **alertes**.

3.  Sous **alertes générales**, activez la case à cocher m’avertir **quand une personne m’ajoute à sa liste de contacts**.

4.  Sous **contacts n’utilisant pas Lync**, sélectionnez **autoriser les invitations, mais bloquer toutes les autres communications**.

5.  Cliquez sur **OK** pour fermer la fenêtre d’options.

</div>

<span> </span>

</div>

</div>

</div>

