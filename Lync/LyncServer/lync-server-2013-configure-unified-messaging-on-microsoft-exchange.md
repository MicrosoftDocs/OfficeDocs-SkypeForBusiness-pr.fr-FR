---
title: 'Lync Server 2013 : configuration de la messagerie unifiée sur Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Cette rubrique décrit comment configurer la messagerie unifiée Exchange sur un serveur Microsoft Exchange pour une utilisation avec la voix entreprise.

<div>


> [!NOTE]  
> Les exemples de cette rubrique fournissent une syntaxe pour la version 2007 d’Exchange Management Shell. Si vous exécutez Exchange 2010 ou Exchange 2013, voir la documentation appropriée telle qu’elle est référencée.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Pour configurer un serveur exécutant la messagerie unifiée Exchange Server

1.  Créez un plan de numérotation d’URI (Uniform Resource Identifier) SIP) pour chacun de vos profils d’emplacements vocaux d’entreprise. Si vous choisissez d’utiliser la console de gestion Exchange, créez un nouveau plan de numérotation avec le paramètre de sécurité **sécurisé (par défaut)**.
    
    <div>
    

    > [!WARNING]  
    > Si vous avez défini votre paramètre de sécurité sur <STRONG>sécurisé par SIP</STRONG> pour exiger le chiffrement pour le trafic SIP uniquement, comme précédemment recommandé, Notez que ce paramètre de sécurité sur un plan de numérotation est insuffisant si le pool frontal est configuré pour exiger le chiffrement, ce qui signifie que le pool nécessite un chiffrement pour le trafic SIP et RTP. Lorsque les paramètres de sécurité du plan de numérotation et du pool ne sont pas compatibles, tous les appels à la messagerie unifiée Exchange à partir du pool frontal échouent, ce qui génère une erreur indiquant que vous avez un paramètre de sécurité non compatible.

    
    </div>
    
    Si vous utilisez Exchange Management Shell, tapez :
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Pour plus d’informations, consultez :
    
      - Pour Office Communications Server 2007, voir la section « création d’un plan de numérotation URI SIP de [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) messagerie unifiée » dans et « nouvelle-UMDialplan : [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)aide d’Exchange 2007 ».
    
      - Pour Exchange 2010, voir « créer un plan de numérotation de [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) messagerie unifiée » à et « nouvelle-UMDialplan : [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)aide d’Exchange 2010 » à l’adresse.
    
      - Pour Exchange 2013, voir « messagerie unifiée » [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)à l’adresse.
    
    <div>
    

    > [!NOTE]  
    > Le fait de sélectionner un niveau de sécurité <STRONG>SIPSecured</STRONG> ou <STRONG>sécurisé</STRONG> dépend du mode d’activation ou de désactivation du protocole SRTP (Secure Real-Time Transport Protocol) pour le chiffrement multimédia. Pour l’intégration de Lync Server 2010 à la messagerie unifiée Exchange, cela doit correspondre au niveau de chiffrement dans la configuration multimédia du serveur Lync. La configuration de média de Lync Server peut être affichée en exécutant l’applet de passe <STRONG>Get-CsMediaConfiguration</STRONG> . Pour plus d’informations, consultez la rubrique Get-CsMediaConfiguration dans la documentation Lync Server Management Shell.<BR>Pour plus d’informations sur la sélection du paramètre de sécurité VoIP approprié, voir <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</A>.

    
    </div>

2.  Exécutez l’applet de commande suivante pour obtenir le nom de domaine complet (FQDN) de chaque plan de numérotation de messagerie unifiée :
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Pour plus d’informations, consultez :
    
      - Pour Exchange 2007, voir « Get-UMDialplan : aide Exchange 2007 » à [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)l’adresse.
    
      - Pour Exchange 2010, voir « Get-UMDialplan : aide Exchange 2010 » à [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)l’adresse.
    
      - Pour Exchange 2013, voir « messagerie unifiée » [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)à l’adresse.

3.  Enregistrez le nom du plan de numérotation de chaque plan de numérotation de messagerie unifiée. En fonction de votre version d’Exchange Server, il est possible que vous deviez utiliser le nom de domaine complet (FQDN) de chaque nom de plan de numérotation ultérieurement pour le nom du plan de numérotation de votre plan de numérotation de messagerie unifiée correspondant aux noms de plan de numérotation.
    
    <div>
    

    > [!NOTE]  
    > Les noms de plan de numérotation de Lync Server doivent correspondre aux noms du plan de numérotation de messagerie unifiée uniquement si le plan de numérotation de messagerie unifié s’exécute sur une version d’Exchange <EM>antérieure</EM> à Exchange 2010 SP1.

    
    </div>

4.  Ajoutez le plan de numérotation au serveur exécutant la messagerie unifiée Exchange en procédant comme suit :
    
      - Si vous choisissez d’utiliser la console de gestion Exchange, vous pouvez ajouter le plan de numérotation à partir de la feuille de propriétés du serveur. Pour obtenir des instructions spécifiques, consultez la documentation du produit Exchange Server.
        
        Pour Exchange 2007, voir la section « Comment ajouter un serveur de messagerie unifiée à un [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)plan de numérotation » à l’adresse.
        
        Pour Exchange 2010, voir « afficher ou configurer les propriétés d’un serveur de messagerie unifiée » [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).
        
        Pour Exchange 2013, voir « messagerie unifiée » [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)à l’adresse.
    
      - Si vous utilisez Exchange Management Shell, exécutez la commande suivante pour chaque serveur Exchange UM :
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Avant de procéder à l’étape suivante, assurez-vous que tous les utilisateurs d’Enterprise Voice ont été configurés avec une boîte aux lettres Exchange Server.<BR>Pour Exchange 2007, voir la bibliothèque TechNet Exchange Server 2007 à <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>l’adresse.<BR>Pour Exchange 2010, voir la bibliothèque TechNet Exchange Server 2010 à <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>l’adresse.<BR>Lorsque vous spécifiez une stratégie de boîte aux lettres pour chaque plan de numérotation que vous avez créé à l’étape 1, sélectionnez la stratégie par défaut ou celle que vous avez créée.

    
    </div>

5.  Naviguez \<jusqu’à scripts\>\\d’annuaire d’installation Exchange, puis, si Exchange est déployé dans une seule forêt, tapez :
    ```console
    exchucutil.ps1
    ```
    Ou, si Exchange est déployé dans plusieurs forêts, tapez :
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    où FQDN de forêt spécifie la forêt dans laquelle le serveur Lync est déployé.
    
    Si vous avez un ou plusieurs plans de numérotation de messagerie unifiée associés à plusieurs passerelles IP, passez à l’étape 6. Si vos plans de numérotation sont associés à une seule passerelle IP, ignorez l’étape 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Assurez-vous de redémarrer le service <STRONG>frontal de Lync Server</STRONG> (rtcsrv. exe) <EM>après avoir</EM> exécuté exchucutil. ps1. Dans le cas contraire, Lync Server ne détectera pas la messagerie unifiée dans la topologie.

    
    </div>

6.  À l’aide d’Exchange Management Shell ou de la console de gestion Exchange, désactivez les appels sortants pour toutes les passerelles IP associées à chacun de vos plans de numérotation.
    
    <div>
    

    > [!NOTE]  
    > Cette étape est nécessaire pour veiller à ce que les appels sortants par le serveur qui exécute la messagerie unifiée Exchange Server vers des utilisateurs externes (par exemple, comme le cas des scénarios de lecture sur le téléphone) passent de manière fiable au pare-feu d’entreprise.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lors de la sélection de la passerelle IP de MU pour autoriser les appels sortants, choisissez celle qui est susceptible de gérer le plus de trafic. N’autorisez pas le trafic sortant par le biais d’une passerelle IP qui se connecte à un pool de directeurs serveur Lync. Evitez également les pools dans un autre site central ou un site de succursale. Vous pouvez utiliser l’une des méthodes suivantes pour empêcher les appels sortants de traverser une passerelle IP :

    
    </div>
    
      - Si vous utilisez Exchange Management Shell, désactivez chaque passerelle IP en exécutant la commande suivante :
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Pour Exchange 2007, voir « Set-UMIPGateway : aide d’Exchange 2007 » [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)à l’adresse.
        
        Pour Exchange 2010, voir « Set-UMIPGateway : aide d’Exchange 2010 » [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)à l’adresse.
    
      - Si vous utilisez la console de gestion Exchange, désactivez la case à cocher **autoriser les appels sortants via cette passerelle IP** .
    
    <div>
    

    > [!IMPORTANT]  
    > Si votre plan de numérotation d’URI SIP de MU est associé à une seule passerelle IP, n’autorisez pas les appels sortants par le biais de cette passerelle.

    
    </div>

7.  Créer un standard automatique de messagerie unifiée pour chaque plan de numérotation Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > N’incluez pas d’espace dans le nom du standard automatique.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Pour plus d’informations, consultez :
    
      - Pour Exchange 2007, voir "nouvelle-UMAutoAttendant : aide d’Exchange 2007" [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)à l’adresse.
    
      - Pour Exchange 2010, voir "nouvelle-UMAutoAttendant : aide d’Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)à l’adresse.
    
    Pour chaque utilisateur, l’étape suivante doit être effectuée lorsque vous avez activé les utilisateurs de Lync Server pour voix entreprise et que vous connaissez leurs URI SIP.

8.  Associez les utilisateurs Exchange UM (qui doivent être configurés avec une boîte aux lettres Exchange) avec le plan de numérotation de messagerie unifiée et créez un URI SIP pour chaque utilisateur.
    
    <div>
    

    > [!NOTE]  
    > Dans l’exemple suivant, le <STRONG>SIPResourceIdentifier</STRONG> doit être l’adresse SIP de l’utilisateur de Lync Server.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Pour plus d’informations, consultez :
    
      - Pour Exchange 2007, voir la section « Activer-UMMailbox : aide Exchange 2007 [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)» à l’adresse.
    
      - Pour Exchange 2010, voir la section « Activer-UMMailbox : aide Exchange 2010 [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)» à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

