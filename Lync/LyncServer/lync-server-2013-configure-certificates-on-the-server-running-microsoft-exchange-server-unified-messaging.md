---
title: 'Lync Server 2013: configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-26_

Si vous avez déployé la messagerie unifiée Exchange, comme décrit dans la section [planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) dans la documentation de planification, et si vous souhaitez fournir des fonctionnalités de messagerie unifiée Exchange aux utilisateurs d’Enterprise Voice dans votre dans l’organisation, vous pouvez utiliser les procédures suivantes pour configurer le certificat sur le serveur exécutant la messagerie unifiée Exchange.

<div>


> [!IMPORTANT]  
> Pour les certificats internes, les serveurs exécutant Lync Server 2013 et les serveurs exécutant Microsoft Exchange doivent disposer de certificats d’autorité racine approuvés qui sont mutuellement approuvés. L’autorité de certification (CA) peut être le même, ou une autre autorité de certification, tant que le certificat racine de l’autorité de certification est inscrit sur les serveurs dans leur magasin de certificats.



</div>

Le serveur Exchange doit être configuré avec un certificat de serveur pour pouvoir se connecter à Lync Server 2013:

1.  Téléchargez le certificat d’autorité de certification du serveur Exchange.

2.  Installez le certificat d’autorité de certification du serveur Exchange.

3.  Vérifiez que la CA figure dans la liste des autorités de certification racines de confiance du serveur Exchange.

4.  Créez une demande de certificat pour le serveur Exchange et installez le certificat.

5.  Attribuez le certificat du serveur Exchange.

<div>

## <a name="to-download-the-ca-certificate"></a>Pour télécharger le certificat d’autorité de certification

1.  Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez **le nom\<http://\>de votre serveur de certification émettrice/certsrv**, puis cliquez sur **OK**.

2.  Sous **Sélectionner une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**.

3.  Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**, sélectionnez **méthode d’encodage pour baser 64**, puis cliquez sur **Télécharger le certificat d’autorité de certification**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez également spécifier le codage DER (Distinguished Encoding Rules) à cette étape. Si vous sélectionnez DER Encoding, le type de fichier à l’étape suivante de cette procédure et à l’étape 10 de <STRONG>pour installer le certificat d’autorité de certification</STRONG> est. p7b plutôt que. cer.

    
    </div>

4.  Dans la boîte de dialogue **téléchargement de fichier** , cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur sur le serveur. (Le fichier aura une extension de fichier. cer ou. p7b, selon le codage que vous avez sélectionné à l’étape précédente.)

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>Pour installer le certificat d’autorité de certification

1.  Sur le serveur exécutant Exchange UM, ouvrez Microsoft Management Console (MMC) en cliquant **sur Démarrer**, sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.

2.  Dans le menu **fichier** , cliquez sur **Ajouter/supprimer un composant logiciel enfichable**, puis cliquez sur **Ajouter**.

3.  Dans la boîte de dialogue **Ajouter des composants logiciels enfichables autonomes** , cliquez sur **certificats**, puis cliquez sur **Ajouter**.

4.  Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.

5.  Dans la boîte de dialogue **Sélectionner un ordinateur** , vérifiez que la case à cocher **ordinateur local: (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.

6.  Cliquez sur **Fermer**, puis cliquez sur **OK**.

7.  Dans l’arborescence de la console, développez **certificats (ordinateur local)**, développez **autorités de certification racine de confiance**, puis cliquez sur **certificats**.

8.  Cliquez avec le bouton droit sur **certificats**, puis cliquez sur **toutes les tâches**et sur **Importer**.

9.  Cliquez sur **Suivant**.

10. Cliquez sur **Parcourir** pour rechercher le fichier, puis cliquez sur **suivant**. (Le fichier aura une extension de fichier. cer ou. p7b, selon le codage que vous avez sélectionné à l’étape 3 de **pour télécharger le certificat d’autorité de certification**.

11. Cliquez sur **Placer tous les certificats dans le magasin suivant**.

12. Cliquez sur **Parcourir**, puis sélectionnez **autorités de certification racines de confiance**.

13. Cliquez sur **suivant** pour vérifier les paramètres, puis cliquez sur **Terminer**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>Pour vérifier que la CA figure dans la liste des autorités de certification racines de confiance

1.  Sur le serveur exécutant la messagerie unifiée Exchange, dans MMC, développez **certificats (ordinateur local)**, développez **autorités de certification racine de confiance**, puis cliquez sur **certificats**.

2.  Dans le volet Détails, vérifiez que votre AC figure dans la liste des autorités de certification approuvées.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Pour configurer la messagerie unifiée Exchange Server 2013 avec Lync Server

1.  Pour plus d’informations, reportez-vous à la section «intégration de la messagerie unifiée Exchange 2013 à Lync Server» dans la documentation sur [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)le serveur Exchange.

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Pour créer une demande de certificat et installer le certificat sur Exchange Server 2007 (SP1)

1.  Sur le serveur exécutant la messagerie unifiée Exchange, cliquez sur **Démarrer**, sur **exécuter**, tapez le nom **\<http://** de votre serveur**\>** de certification émettrice/certsrv, puis cliquez sur **OK**.

2.  Sous **Sélectionner une tâche**, cliquez sur **demander un certificat**.

3.  Sous **demander un certificat**, cliquez sur **demande de certificat avancée**.

4.  Sous **demande de certification avancée**, cliquez sur **créer et demander une demande à cette autorité de certification**.

5.  Sous **demande de certification avancée**, sélectionnez **serveur Web** ou un autre modèle de certificat serveur configuré pour l’authentification du serveur.

6.  Sous **informations d’identification pour le modèle hors connexion**, dans la zone **nom** , tapez le nom de domaine complet (FQDN) du serveur Exchange.
    
    <div>
    

    > [!NOTE]  
    > Vous devez entrer le nom de domaine complet (FQDN) du serveur Exchange sur lequel les communications fonctionneront.

    
    </div>

7.  Sous **options**de la clé, cliquez sur la case à cocher **stocker le certificat dans le magasin de certificats de l’ordinateur local** .

8.  Cliquez sur le bouton de **soumission** en bas de la page Web.

9.  Dans la boîte de dialogue qui s’affiche, cliquez sur **Oui**.

10. Sur la page certificat émis, sous **certificat émis**, cliquez sur **installer ce certificat**.

11. Dans la boîte de dialogue qui s’affiche, cliquez sur **Oui**.

12. Vérifiez que le message «votre nouveau certificat a été correctement installé» s’affiche.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Pour créer un certificat sur Exchange Server 2010

1.  Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec des droits d’utilisateur appropriés. Pour plus d’informations, consultez la section «autorisations [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)d’accès client».

2.  Pour créer le certificat, consultez les procédures suivantes:
    
    1.  "Créer un nouveau certificat Exchange" à[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  «Importer un certificat Exchange» à[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Pour le <STRONG>nom du sujet</STRONG>du certificat, vous devez entrer le nom de domaine complet (FQDN) du serveur Exchange sur lequel les communications doivent fonctionner.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Pour attribuer le certificat sur Exchange Server 2007 (SP1)

1.  Sur le serveur exécutant la messagerie unifiée Exchange, ouvrez la console MMC.

2.  Dans l’arborescence de la console, développez **personnel** , puis cliquez sur **certificats**.

3.  Dans le volet Détails, assurez-vous que le certificat personnel est affiché.

4.  Double-cliquez sur le certificat pour lire ses détails et vérifier qu’il est valide.
    
    <div>
    

    > [!NOTE]  
    > Le certificat est susceptible de prendre quelques minutes avant d’être affiché comme valide.

    
    </div>

5.  Redémarrez le service de messagerie unifiée Microsoft Exchange.
    
    <div>
    

    > [!NOTE]  
    > Le serveur exécutant la messagerie unifiée Exchange Server 2007 SP1 récupère automatiquement le certificat approprié.

    
    </div>

6.  Ouvrez l’observateur d’événements et recherchez l’ID d’événement 1112, qui indique le certificat sur lequel le serveur exécutant la messagerie unifiée Exchange Server 2007 SP1 a récupéré.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Pour attribuer le certificat sur Exchange Server 2010

1.  Ouvrez une session sur le serveur exécutant la messagerie unifiée Exchange avec des droits d’utilisateur appropriés. Pour plus d’informations, consultez la section «autorisations [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)d’accès client».

2.  Pour obtenir la procédure d’affectation d’un certificat, voir «attribuer des services à un [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)certificat» à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

