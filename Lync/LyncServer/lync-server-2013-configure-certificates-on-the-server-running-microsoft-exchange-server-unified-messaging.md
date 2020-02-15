---
title: 'Lync Server 2013 : configuration des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2885b3610c1edce441c6abbd93a2515fa6cb904
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

Si vous avez déployé la messagerie unifiée Exchange, comme décrit dans la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) dans la documentation de planification, et que vous souhaitez fournir des fonctionnalités de messagerie unifiée Exchange aux utilisateurs de voix entreprise de votre organisation, vous pouvez utiliser les procédures suivantes pour configurer le certificat sur le serveur exécutant la messagerie unifiée Exchange.

<div>


> [!IMPORTANT]  
> Pour les certificats internes, les serveurs exécutant Lync Server 2013 et les serveurs exécutant Microsoft Exchange doivent avoir des certificats d’autorité racine approuvés qui sont mutuellement approuvés. L’autorité de certification (CA) peut être la même ou une autre autorité de certification, tant que le certificat racine de l’autorité de certification est inscrit dans le magasin de certificats de l’autorité racine approuvée.



</div>

Le serveur Exchange doit être configuré avec un certificat de serveur afin de se connecter à Lync Server 2013 :

1.  Téléchargez le certificat d’autorité de certification du serveur Exchange Server.

2.  Installez le certificat d’autorité de certification du serveur Exchange Server.

3.  Vérifiez que l’autorité de certification figure dans la liste des autorités de certification racines de confiance du serveur Exchange Server.

4.  Créez une demande de certificat pour le serveur Exchange Server et installez le certificat.

5.  Assignez le certificat du serveur Exchange Server.

<div>

## <a name="to-download-the-ca-certificate"></a>Pour télécharger le certificat de l’autorité de certification

1.  Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **http://\<nom de\>votre autorité de certification serveur/certsrv**, puis cliquez sur **OK**.

2.  Sous **Sélectionnez une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation de certificats**.

3.  Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une liste de révocation**de certificats, sélectionnez **méthode de codage pour baser 64**, puis cliquez sur Télécharger le certificat de l' **autorité de certification**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez également spécifier le codage DER (Distinguished Encoding Rules) à cette étape. Si vous sélectionnez cette méthode, le fichier spécifié à l’étape suivante de cette procédure et à l’étape 10 de la procédure <STRONG>Pour installer le certificat de l’autorité de certification</STRONG> sera de type .p7b et non .cer.

    
    </div>

4.  Dans la boîte de dialogue **Téléchargement de fichier**, cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur du serveur (le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage que vous avez sélectionnée à l’étape précédente).

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>Pour installer le certificat de l’autorité de certification

1.  Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez la console MMC (Microsoft Management Console) en cliquant sur **Démarrer**, sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.

2.  Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.

3.  Dans la zone **Ajout d’un composant logiciel enfichable autonome**, cliquez sur **Certificats**, puis sur **Ajouter**.

4.  Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.

5.  Dans la boîte de dialogue **Sélectionner un ordinateur** , vérifiez que la case à cocher **ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.

6.  Cliquez sur **Fermer**, puis sur **OK**.

7.  Dans l’arborescence de la console, développez **Certificats (ordinateur local)**, développez **Autorités de certification racines de confiance**, puis cliquez sur **Certificats**.

8.  Cliquez avec le bouton droit sur **Certificats**, cliquez sur **Toutes les tâches**, puis sur **Importer**.

9.  Cliquez sur **Suivant**.

10. Cliquez sur **Parcourir** pour localiser le fichier, puis cliquez sur **Suivant**. Le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage sélectionnée à l’étape 3 de la procédure **Pour télécharger le certificat de l’autorité de certification**.

11. Cliquez sur **Placer tous les certificats dans le magasin suivant**.

12. Cliquez sur **Parcourir**, puis sélectionnez **Autorités de certification racines de confiance**.

13. Cliquez sur **Suivant** pour vérifier les paramètres, puis sur **Terminer**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>Pour vérifier que l’autorité de certification figure sur la liste des autorités de certification racines de confiance

1.  Sur le serveur exécutant la messagerie unifiée Exchange, dans la console MMC, développez **certificats (ordinateur local)**, développez **autorités de certification racines de confiance**, puis cliquez sur **certificats**.

2.  Dans le volet de détail, vérifiez que votre autorité de certification figure sur la liste des autorités de certification de confiance.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Pour configurer la messagerie unifiée Exchange Server 2013 avec Lync Server

1.  Pour plus d’informations, voir « intégration de la messagerie unifiée Exchange 2013 avec Lync Server » [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)dans la documentation d’Exchange Server à l’adresse.

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Pour créer une demande de certificat et installer le certificat sur Exchange Server 2007 (SP1)

1.  Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **\<http://** nom de votre autorité de certification serveur**\>/certsrv**, puis cliquez sur **OK**.

2.  Sous **Sélectionner une tâche**, cliquez sur **Demander un certificat**.

3.  Sous **Demander un certificat**, cliquez sur **Demande de certificat avancée**.

4.  Sous **Demande de certificat avancée**, cliquez sur **Créer et soumettre une demande de certification auprès de cette Autorité de certification**.

5.  Sous **Demande de certificat avancée**, sélectionnez **Serveur web** ou un autre modèle de certificat du serveur configuré pour l’authentification du serveur.

6.  Sous **informations d’identification pour le modèle hors connexion**, dans la zone **nom** , tapez le nom de domaine complet (FQDN) du serveur Exchange.
    
    <div>
    

    > [!NOTE]  
    > Vous devez entrer le nom de domaine complet du serveur Exchange Server pour que les communications fonctionnent.

    
    </div>

7.  Sous **Options de la clé**, activez la case à cocher **Stocker le certificat dans le magasin de certificats de l’ordinateur local**.

8.  Cliquez sur le bouton **Envoyer** en bas de la page web.

9.  Dans la boîte de dialogue de confirmation qui s’affiche, cliquez sur **Oui**.

10. Dans la page Certificat émis, sous **Certificat émis**, cliquez sur **Installer ce certificat**.

11. Dans la boîte de dialogue de confirmation qui s’affiche, cliquez sur **Oui**.

12. Vérifiez que le message « Votre nouveau certificat a été correctement installé » s’affiche.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Pour créer un certificat sur Exchange Server 2010

1.  Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec les droits d’utilisateur appropriés. Pour plus d’informations, voir « autorisations d’accès [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)au client » à l’adresse.

2.  Suivez les procédures ci-après pour créer le certificat :
    
    1.  « Créer un nouveau certificat Exchange » à l’adresse[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  « Importer un certificat Exchange » à l’adresse[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Pour le <STRONG>Nom du sujet</STRONG> du certificat, vous devez entrer le nom de domaine complet du serveur Exchange Server pour que les communications fonctionnent.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Pour attribuer le certificat au serveur Exchange Server 2007 (SP1)

1.  Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez la console MMC.

2.  Dans l’arborescence de la console, développez **Personnel** puis cliquez sur **Certificats**.

3.  Dans le volet de détail, vérifiez que le certificat personnel est bien affiché.

4.  Double-cliquez sur le certificat pour lire ses détails et vérifier qu’il est valide.
    
    <div>
    

    > [!NOTE]  
    > Cela peut prendre quelques minutes avant que le certificat s’affiche comme étant valide.

    
    </div>

5.  Redémarrez le service de messagerie unifiée Microsoft Exchange.
    
    <div>
    

    > [!NOTE]  
    > Le serveur qui exécute la messagerie unifiée Exchange Server 2007 SP1 récupère automatiquement le bon certificat.

    
    </div>

6.  Ouvrez l’Observateur d’événements et recherchez l’ID de l’événement 1112. Il indique le certificat récupéré par le serveur exécutant la messagerie unifiée Exchange Server 2007 SP1.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Pour attribuer le certificat au serveur Exchange Server 2010

1.  Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec les droits d’utilisateur appropriés. Pour plus d’informations, voir « autorisations d’accès [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)au client » à l’adresse.

2.  Pour obtenir la procédure d’attribution du certificat, consultez la rubrique « attribuer des services à [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)un certificat » à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

