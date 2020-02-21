---
title: 'Lync Server 2013 : utilisation de la connectivité Lync-Skype en tant qu’utilisateur final'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6971ef2d6fb08838a4fcf71f4fec8097a7f9e47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-27_

Lync-Skype Connectivity permet aux utilisateurs Skype et aux utilisateurs de Lync de s’ajouter eux-mêmes sous forme de contacts, d’échanger des messages instantanés et d’effectuer des appels audio et vidéo. Lorsqu’un utilisateur Skype ajoute un utilisateur Lync, un utilisateur Skype crée un contact dans Skype contenant l’URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) de l’utilisateur Lync. À l’inverse, lorsqu’un utilisateur Lync ajoute un contact Skype, l’utilisateur de Lync crée un contact dans Lync qui contiendra le compte Microsoft (MSA) de l’utilisateur Skype, et non le nom d’utilisateur Skype.

**Qu’est-ce qu’un MSA ?** Les utilisateurs de Skype doivent se connecter à Skype à l’aide d’un compte Microsoft (anciennement appelé Windows Live ID) pour communiquer avec les contacts Lync.Un compte Microsoft est constitué de la combinaison d’une adresse de messagerie et d’un mot de passe, que vous pouvez également utiliser pour vous connecter à des services tels que la technologie de stockage Microsoft OneDrive, Windows Phone, le service de jeux Microsoft Xbox LIVE Online et la messagerie Microsoft Outlook. et le client de collaboration (et, auparavant, le service de messagerie Web Microsoft Hotmail ou Windows Live Messenger).Si vous utilisez une adresse de messagerie et un mot de passe pour vous connecter à ces services ou à d’autres services, vous disposez déjà d’un compte Microsoft.Pour plus d’informations sur la création d’un compte Microsoft, reportez-vous [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)à la page d’inscription au compte Microsoft à l’adresse. Vous pouvez fusionner votre compte Skype existant avec votre compte Microsoft pour l’authentification unique, par le biais d’une variété d’applications et de services. Une fois le compte fusionné, un utilisateur de Skype peut envoyer une demande de contact aux utilisateurs de Lync.

<div>


> [!IMPORTANT]  
> Pour permettre aux utilisateurs Lync et Skype de communiquer entièrement les uns avec les autres, les conditions suivantes doivent être remplies : 
> <UL>
> <LI>
> <P>Les utilisateurs de Skype doivent être connectés à leur client Skype à l’aide d’un compte Microsoft (MSA).</P>
> <LI>
> <P>Les utilisateurs de Lync doivent être activés pour la connectivité PIC par leur administrateur Lync.</P>
> <LI>
> <P>Lorsqu’un utilisateur Skype ajoute un contact Lync, vérifiez que le mot Lync apparaît sous le nom du contact. Cela indique qu’un URI Lync a été trouvé.</P>
> <LI>
> <P>Lorsqu’un utilisateur Skype ajoute un contact Lync et que les résultats de la recherche ne sont pas renvoyés pour ce domaine Lync, le processus de mise en service PIC n’est peut-être pas terminé ou le domaine Lync n’a pas encore été configuré.</P>
> <LI>
> <P>En fonction des paramètres de confidentialité des utilisateurs Lync et Skype, la messagerie instantanée, la vidéo et la présence peuvent ne pas fonctionner tant que les nouveaux contacts ne sont pas acceptés par chaque utilisateur.</P></LI></UL>



</div>

**Pour ajouter un contact Skype à Lync 2013**

1.  Dans Lync, cliquez sur **Ajouter un contact, puis ajoutez un contact qui n’est pas dans mon organisation**.

2.  Dans la liste des fournisseurs de contacts disponibles, sélectionnez **Skype**.

3.  Dans le champ **adresse de messagerie instantanée** , entrez le compte Microsoft (MSA) de l’utilisateur Skype.

4.  Dans la zone de liste déroulante **Ajouter au groupe de contacts** , sélectionnez un groupe de contacts auquel ajouter l’utilisateur.

5.  Dans la liste déroulante **définir la relation de confidentialité** , sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.

6.  L’utilisateur s’affiche désormais en tant que contact dans Lync. Sélectionnez l’utilisateur, cliquez avec le bouton droit sur le nom de l’utilisateur, puis cliquez sur **afficher la carte de visite** pour afficher les propriétés de l’utilisateur. Vous pouvez désormais établir un appel audio ou vidéo avec le nouvel utilisateur Skype ajouté.

Pour plus d’informations sur la prise en charge des contacts, consultez [la rubrique ajouter un contact dans Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).

Lorsque le compte Microsoft d’un utilisateur Skype utilise un nom de domaine personnalisé, tel que <strong>Bob@contoso.com</strong> , un utilisateur Lync peut ajouter ce compte Microsoft à Lync de deux manières :

1.  Utilisez l’icône **Ajouter un contact** ou

2.  Utilisez la zone **Rechercher une personne ou une salle, ou un champ de numéro de** téléphone.

Dans chaque instance, l’utilisateur Lync doit entrer le courrier électronique de l’utilisateur Skype dans le format suivant : <strong>utilisateur (nom de domaine) @msn. com</strong> .

<div>


> [!IMPORTANT]  
> Cette étape n’est pas obligatoire pour les comptes Microsoft qui utilisent les noms de domaine suivants : <STRONG>@live. com, @hotmail. com ou @outlook. com</STRONG>. Pour plus d’informations sur les noms de domaine personnalisés pris en charge, consultez la rubrique <A href="https://support.microsoft.com/kb/897567">domaines de messagerie instantanée publics pris en charge</A>.



</div>

**Pour ajouter un contact Skype à Lync lors de l’utilisation d’un nom de domaine personnalisé**

1.  Dans Lync, cliquez sur **Ajouter un contact, puis ajoutez un contact qui n’est pas dans mon organisation**.

2.  Dans la liste des fournisseurs de contacts disponibles, sélectionnez **Skype**.

3.  Dans le champ **adresse de messagerie instantanée** , entrez le compte Microsoft (MSA) de l’utilisateur Skype au format <strong>utilisateur (nom de domaine) @msn. com</strong>. Ainsi, pour l’utilisateur bob@contoso.com, l’entrée <strong>serait Bob (contoso. com) @msn.<strong> com.

4.  Dans la zone de liste déroulante **Ajouter au groupe de contacts** , sélectionnez un groupe de contacts auquel ajouter l’utilisateur.

5.  Dans la zone de liste déroulante **définir la relation de confidentialité** , sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.

6.  Un utilisateur Lync peut également utiliser la commande **Rechercher une personne ou une salle, ou composer un** champ de numéro dans Lync, et ajouter une adresse semblable à l' <strong>utilisateur suivant (nom de domaine) @msn. com</strong> . Ainsi, pour le compte Microsoft bob@contoso.com, l’entrée serait <strong>Bob (contoso. com) @msn. com</strong> .

7.  Suivez les étapes 4 et 5 plus haut dans cette procédure pour ajouter le contact à un groupe de contacts et sélectionner la relation de confidentialité appropriée.

**Pour ajouter un contact Lync à Skype**

1.  Connectez-vous à Skype. L’utilisateur Skype doit être connecté à son client Skype à l’aide d’un compte Microsoft (MSA).

2.  Sélectionnez l’icône Ajouter des contacts.

3.  Entrez l’URI SIP de l’utilisateur Lync. (par exemple, bob@contoso.com).

4.  Lorsque Skype trouve la correspondance dans les résultats de la recherche, recherchez le mot **Lync** sous le nom de l’utilisateur Lync. Cela indique que Skype a réussi à localiser l’URI SIP du client Lync. Cliquez sur le nom.

5.  Dans le coin supérieur droit de la fenêtre, cliquez sur Ajouter aux contacts.

6.  Le nouveau contact est maintenant ajouté à votre liste de contacts, mais un point d’interrogation s’affiche au lieu de son icône d’État jusqu’à ce qu’il accepte votre requête. Lorsque votre nouveau contact accepte votre demande, vous pouvez voir quand il est en ligne, initier des conversations par messagerie instantanée et émettre des appels audio et vidéo.
    
    <div>
    

    > [!IMPORTANT]  
    > L’administrateur Lync Server doit configurer les paramètres de stratégie de l’utilisateur Lync pour autoriser les demandes entrantes. Si ce n’est pas le cas, l’utilisateur de Lync ne reçoit pas de demandes de contact de la part de l’utilisateur Skype. En fonction de la configuration des paramètres de stratégie de l’utilisateur Lync, la demande d’ajout de l’utilisateur Skype apparaît dans le <STRONG>nouvel</STRONG> onglet du client Lync. Pour commencer à communiquer avec l’utilisateur Skype, l’utilisateur de Lync doit ajouter l’utilisateur Skype à la liste des favoris ou à une liste de contacts. L’image ci-dessous montre l’emplacement du <STRONG>nouvel</STRONG> onglet dans le client Lync.

    
    </div>

Un utilisateur Lync doit configurer des alertes Lync pour s’assurer que les demandes envoyées à partir d’un utilisateur Skype apparaissent et sont détectables par l’utilisateur de Lync. Pour configurer les alertes Lync, exécutez la procédure suivante.

**Pour configurer les alertes Lync**

1.  À partir du client Lync, cliquez sur l’icône **options** .

2.  Sélectionnez **alertes**.

3.  Sous **alertes générales**, sélectionnez m' **indiquer quand quelqu’un m’ajoute à sa liste de contacts**.

4.  Sous **contacts n’utilisant pas Lync**, sélectionnez **autoriser les invitations, mais bloquer toutes les autres communications**.

5.  Cliquez sur **OK** pour fermer la fenêtre Options.

</div>

<span> </span>

</div>

</div>

</div>

