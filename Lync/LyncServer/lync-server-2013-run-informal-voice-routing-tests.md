---
title: 'Lync Server 2013 : exécuter des tests de routage des communications vocales informelles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 851d292e4c1f891eefa9abb4126ac74e7f3469cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Exécuter des tests de routage des communications vocales informels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-07_

Vous pouvez utiliser la boîte de dialogue **Créer des informations de cas de test de routage des communications vocales** pour effectuer des tests informels avant de lancer un cas de test réel. Lorsque vous êtes satisfait du résultat d’un test, vous pouvez l’enregistrer comme un cas de test formel.

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>Pour effectuer un test de routage des communications vocales informel

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.

4.  Dans la page **Tester le routage des com. vocales**, cliquez sur **Créer des informations de cas de test de routage des communications vocales**.

5.  Dans le champ **Numéro composé**, entrez le numéro de téléphone à utiliser pour ce test. Ce numéro sera normalisé et affiché dans le champ **Numéro normalisé** du volet **Résultats**.

6.  Dans la liste **Plan de numérotation**, sélectionnez le plan de numérotation à utiliser pour tester le numéro composé. Le plan de numérotation global est utilisé par défaut.
    
    Lorsque vous exécutez le test, la première règle de normalisation de ce plan de numérotation correspondant au numéro composé apparaîtra dans le champ **Règle de normalisation** du volet **Résultats**.

7.  Dans la liste **Stratégie de voix**, sélectionnez la stratégie de voix à utiliser pour tester le numéro composé. La stratégie de voix globale est utilisée par défaut.
    
    Lorsque vous exécutez le test, le premier enregistrement d’utilisation PSTN correspondant de cette stratégie de voix s’affichera dans le champ **Première utilisation PSTN** du volet **Résultats**. Le premier routage des communications vocales correspondant associé à cet enregistrement d’utilisation PSTN apparaîtra également dans le champ **Premier itinéraire**.

8.  (Optionnel) Activez la case à cocher **Remplir à partir de l’utilisateur** pour tester le numéro composé par rapport à la stratégie de voix attribuée à un utilisateur particulier.
    
    1.  Cliquez sur **Parcourir** pour afficher la boîte de dialogue **Sélectionner des utilisateurs Voix Entreprise**.
    
    2.  Cliquez sur **Rechercher** pour afficher la liste des utilisateurs activés pour Voix Entreprise.
    
    3.  Double-cliquez sur le nom d’utilisateur dont vous souhaitez utiliser la stratégie de voix attribuée pour ce test. Le champ **Stratégie** affiche à présent la stratégie de voix attribuée à l’utilisateur sélectionné.
    
    Lorsque vous exécutez le test, le premier enregistrement d’utilisation réseau téléphonique commuté (PSTN) correspondant de cette stratégie de voix s’affichera dans le champ **Première utilisation PSTN** du volet **Résultats**. Le premier routage des communications vocales correspondant associé à cet enregistrement d’utilisation PSTN apparaîtra également dans le champ **Premier itinéraire**.

9.  Cliquez sur **Exécuter** pour lancer le cas de test. Les résultats s’affichent dans le panneau droit de la boîte de dialogue.

10. (Optionnel) Cliquez sur **Enregistrer sous** pour enregistrer la configuration de test comme un cas de test formel.
    
    1.  Dans le champ **Nom** de la boîte de dialogue **Enregistrer les informations de cas de test de routage des communications vocales**, entrez le nom unique de ce cas de test.
        
        Le nom doit être unique parmi tous les cas de test de routage des communications vocales dans votre déploiement Voix Entreprise. Il peut comporter jusqu’à 32 caractères et peut contenir des caractères alphanumériques, outre la barre oblique inverse (\\), le point (.) ou le trait de soulignement (\_).
    
    2.  Notez que les champs restants de la boîte de dialogue **Enregistrer les informations de cas de test de routage des communications vocales** sont en lecture seule et préremplis à partir de la configuration *et* des résultats du test informel. Vérifiez qu’il s’agit effectivement de la configuration à enregistrer pour le cas de test.
        
        <div>
        

        > [!NOTE]  
        > Les valeurs des résultats du test servent à préremplir les champs de la boîte de dialogue <STRONG>Enregistrer les informations de cas de test de routage des communications vocales</STRONG> de la façon suivante : 
        > <UL>
        > <LI>
        > <P>Le champ <STRONG>Traduction attendue</STRONG> est prérempli avec la valeur du champ <STRONG>Numéro normalisé</STRONG>.</P>
        > <LI>
        > <P>Le champ <STRONG>Itinéraire attendu</STRONG> est prérempli avec la valeur du champ <STRONG>Premier itinéraire</STRONG>.</P>
        > <LI>
        > <P>Le champ <STRONG>Utilisation PSTN attendue</STRONG> est prérempli avec la valeur du champ <STRONG>Première utilisation PSTN</STRONG>.</P></LI></UL>Si le test ne renvoie aucun résultat pour ces valeurs, le champ correspondant apparaît vide dans la boîte de dialogue <STRONG>Enregistrer les informations de cas de test de routage des communications vocales</STRONG>.</div>
    
    3.  Cliquez sur **Ok** pour enregistrer le cas de test, ou sur **Annuler** pour revenir à la boîte de dialogue **Afficher les informations de cas de test de routage des communications vocales** pour poursuivre le test avant de l’enregistrer.

11. Cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > À chaque fois que vous créez un cas de test de routage des communications vocales, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier le cas de test. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer un cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-routing-test-case.md)  
[Exécuter des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-run-voice-routing-test-cases.md)  
[Exporter des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importer des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

