---
title: 'Lync Server 2013: création d’un itinéraire vocal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4c6a9492cbbecafff95a1f6e626087e79f62d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>Créer un itinéraire vocal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

La procédure suivante vous explique comment créer un nouvel itinéraire vocal à l’aide du panneau de configuration de Lync Server 2013. Pour modifier un itinéraire existant, reportez-vous à la rubrique [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md) pour la procédure.

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>Pour créer un itinéraire vocal à l’aide du panneau de configuration de Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Cliquez sur **Itinéraire**.

5.  Cliquez sur **Nouveau** pour afficher la boîte de dialogue **Nouvel itinéraire des communications vocales**.

6.  Dans **Nom**, tapez un nom descriptif pour l’itinéraire des communications vocales.

7.  (Facultatif) Dans **Description**, tapez une description complémentaire du nouvel itinéraire des communications vocales.

8.  Pour spécifier les modèles que cet itinéraire doit prendre en compte, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre** ou l’écrire manuellement.
    
      - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
        
          - **Chiffres de départ pour les nombres que vous souhaitez autoriser:** Entrez les valeurs de préfixe que ce routage doit accepter (y compris les touches de début + si nécessaire). Par exemple, tapez **+ 425**, puis cliquez sur **Ajouter**. Répétez cette procédure pour chaque valeur de préfixe que vous voulez inclure dans l’itinéraire.
        
          - **Exceptions:** Si vous voulez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillance le préfixe et cliquez sur **exceptions**. Tapez une ou plusieurs valeurs pour les modèles correspondants pour lesquels vous ne souhaitez *pas* que cet itinéraire puisse être pris en charge. Par exemple, pour exclure les nombres commençant par + 425237 de l’itinéraire, entrez la valeur **+ 425237** dans le champ **exceptions** , puis cliquez sur **OK**.
    
      - Pour définir manuellement le modèle de correspondance, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis entrez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus d’informations sur la façon d’écrire des expressions régulières, voir «expressions [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)régulières .NET Framework» à l’adresse.

9.  Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché pour le destinataire. Si vous sélectionnez cette option, vous devez spécifier un **autre ID de l’appelant** qui s’affichera pour l’ID d’appelant du destinataire.

10. Pour associer une ou plusieurs jonctions à l’itinéraire des communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.
    
    <div>
    

    > [!NOTE]  
    > Si votre déploiement inclut des serveurs de médiation Microsoft Office Communications Server 2007 R2, ils sont également disponibles dans la liste.

    
    </div>

11. Pour associer une ou plusieurs utilisations de réseau téléphonique commuté (PSTN) à la route, cliquez sur **Sélectionner** et sélectionnez un enregistrement dans la liste des enregistrements d’utilisation RTC définis pour votre déploiement voix entreprise.
    
    <div>
    

    > [!NOTE]  
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation RTC disponibles, voir <A href="lync-server-2013-view-pstn-usage-records.md">afficher les enregistrements d’utilisation RTC dans Lync Server 2013</A>.<BR>Pour créer ou modifier des enregistrements d’utilisation RTC, voir <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">créer une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013</A>.

    
    </div>

12. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez son nom, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!NOTE]  
    > Contrairement à une stratégie de voix, l’ordre dans lequel les enregistrements d’utilisation RTC sont répertoriés dans l’itinéraire des communications vocales n’a pas d’importance. Nous vous recommandons, toutefois, d’organiser la liste par fréquence d’utilisation. Par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server parcourt la liste à partir du haut vers le bas.)

    
    </div>

13. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez enregistrer un itinéraire vocal qui ne transmet pas encore le test et le reconfigurer plus tard. Pour plus d’informations, consultez <A href="lync-server-2013-test-voice-routing.md">tester le routage vocal dans Lync Server 2013</A>.

    
    </div>

14. Cliquez sur **OK** pour enregistrer l’itinéraire des communications vocales.

<div>


> [!IMPORTANT]  
> Quand vous créez un itinéraire des communications vocales, vous devez exécuter la commande <STRONG>Tout valider</STRONG> pour publier la configuration modifiée. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement vocal dans Lync Server 2013</A>



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Afficher les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Créer une stratégie de voix et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

