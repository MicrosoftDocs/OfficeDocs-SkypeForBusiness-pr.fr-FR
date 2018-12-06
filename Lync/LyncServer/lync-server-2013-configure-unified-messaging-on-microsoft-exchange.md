---
title: Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013
TOCTitle: Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398129(v=OCS.15)
ms:contentKeyID: 49296151
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique décrit comment configurer la messagerie unifiée Exchange sur un serveur Microsoft Exchange Server en vue de son utilisation avec Voix Entreprise.

> [!NOTE]  
> Les exemples d’applet de commande dans cette rubrique indiquent la syntaxe pour la version d’Exchange 2007 de l’environnement de ligne de commande Exchange Management Shell. Si vous exécutez Exchange 2010 ou Exchange 2013, reportez-vous à la documentation appropriée indiquée.

## Pour configurer un serveur exécutant la messagerie unifiée Exchange Server

1.  Créez un plan de numérotation URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) de messagerie unifiée pour chacun des profils d’emplacement Voix Entreprise. Si vous choisissez d’utiliser la console de gestion Exchange, créez un nouveau plan de numérotation avec le paramètre de sécurité **Secured (de préférence)**.
    
    > [!WARNING]  
    > Si vous définissez la valeur du paramètre de sécurité sur <strong>SIP Secured</strong> pour exiger le chiffrement uniquement pour le trafic SIP, comme précédemment recommandé, notez que ce paramètre de sécurité sur un plan de numérotation est insuffisant si le pool frontal est configuré pour exiger le chiffrement, ce qui signifie que le pool exige le chiffrement pour le trafic SIP et RTP. Lorsque les paramètres de sécurité du pool et du plan de numérotation ne sont pas compatibles, tous les appels vers la messagerie unifiée Exchange depuis le pool frontal échoueront. Une erreur indiquant « Paramètre de sécurité incompatible » est alors générée.    
    Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, tapez :
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    Pour plus d’informations, consultez :
    
      - Pour Office Communications Server 2007, consultez « Procédure de création d’un plan de numérotation URI SIP de messagerie unifiée » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268632\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268632%26clcid=0x40c) et « New-UMDialplan : aide de Microsoft Exchange 2007 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268666\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268666%26clcid=0x40c).
    
      - Pour Exchange 2010, consultez « Créer un plan de numérotation de messagerie unifiée » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268674\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268674%26clcid=0x40c) et « New-UMDialplan : aide de Microsoft Exchange 2010 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268680\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268680%26clcid=0x40c).
    
      - Pour Exchange 2013, consultez « Messagerie unifiée » à l’adresse [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x40c).
    
    > [!NOTE]  
    > La sélection du niveau de sécurité <strong>SIPSecured</strong> ou <strong>Secured</strong> dépend de l’activation ou de la désactivation du protocole SRTP (Secure Real-time Transport Protocol) pour le chiffrement multimédia. Pour l’intégration de Lync Server 2010 à la messagerie unifiée Exchange, ce niveau de sécurité doit correspondre au niveau de chiffrement dans la configuration multimédia de Lync Server. Pour afficher la configuration multimédia de Lync Server, exécutez l’applet de commande <strong>Get-CsMediaConfiguration</strong>. Pour plus d’informations, consultez Get-CsMediaConfiguration dans la documentation de Lync Server Management Shell.<br />
    Pour plus d’informations sur la sélection du paramètre Sécurité VoIP approprié, consultez <a href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</a>.

2.  Exécutez l’applet de commande suivante pour obtenir le nom de domaine complet (FQDN) pour chaque plan de numérotation de messagerie unifiée :
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Pour plus d’informations, consultez :
    
      - Pour Exchange 2007, consultez « Get-UMDialplan : aide de Microsoft Exchange 2007 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268678\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268678%26clcid=0x40c).
    
      - Pour Exchange 2010, consultez « Get-UMDialplan : aide de Microsoft Exchange 2010 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268679\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268679%26clcid=0x40c).
    
      - Pour Exchange 2013, consultez « Messagerie unifiée » à l’adresse [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x40c).

3.  Enregistrez le nom de chaque plan de numérotation de messagerie unifiée. En fonction de votre version d’Exchange Server, il se peut que vous deviez utiliser plus tard le nom de domaine complet de chaque plan de numérotation comme nom de plan de numérotation Lync Server correspondant de chaque plan de numérotation de messagerie unifiée pour que les noms de plan de numérotation correspondent.
    
    > [!NOTE]  
    > Les noms de plan de numérotation Lync Server doivent correspondre aux noms de plan de numérotation de messagerie unifiée uniquement si le plan de numérotation de messagerie unifiée fonctionne sur une version d’Exchange <em>antérieure</em> à Exchange 2010 SP1.

4.  Ajoutez le plan de numérotation au serveur exécutant la messagerie unifiée Exchange comme suit :
    
      - Si vous choisissez d’utiliser la console de gestion Exchange, vous pouvez ajouter le plan de numérotation à partir de la feuille de propriétés du serveur. Pour des instructions spécifiques, voir la documentation du produit Exchange Server.
        
        Pour Exchange 2007, consultez « Procédure d’ajout d’un serveur de messagerie unifiée à un plan de numérotation » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268681\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268681%26clcid=0x40c).
        
        Pour Exchange 2010, consultez « Afficher ou configurer les propriétés d’un serveur de messagerie unifiée » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268682\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268682%26clcid=0x40c).
        
        Pour Exchange 2013, consultez « Messagerie unifiée » à l’adresse [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x40c).
    
      - Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, exécutez ce qui suit pour chaque serveur de messagerie unifiée Exchange :
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umserver -instance $ums[0]
    
    > [!NOTE]  
    > Avant d’effectuer l’étape suivante, vérifiez que tous les utilisateurs de Voix Entreprise ont été configurés avec une boîte aux lettres Exchange Server.<br />
    Pour Exchange 2007, consultez la bibliothèque TechNet Exchange Server 2007 à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=268685%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=268685&amp;clcid=0x40C</a>.<br />
    Pour Exchange 2010, consultez la bibliothèque TechNet Exchange Server 2010 à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=268686%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=268686&amp;clcid=0x40C</a>.<br />
    Lorsque vous spécifiez une stratégie de boîte aux lettres pour chaque plan de numérotation créé à l’étape 1, vous pouvez sélectionner la stratégie par défaut ou une stratégie que vous avez créée.

5.  Accédez au \<*répertoire d’installation Exchange*\>\\Scripts, et si Exchange est déployé dans une seule forêt, tapez ceci :
    
        exchucutil.ps1
    
    Ou, si Exchange est déployé dans plusieurs forêts, tapez ceci :
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    où *Nom de domaine complet de la forêt* représente la forêt dans laquelle Lync Server est déployé.
    
    Si vous avez un ou plusieurs plans de numérotation de messagerie unifiée associés à plusieurs passerelles IP, passez à l’étape 6. Si chaque plan de numérotation est associé à une seule passerelle IP, ignorez l’étape 6.
    
    > [!IMPORTANT]  
    > Redémarrez le service <strong>Serveur principal Lync Server</strong> (rtcsrv.exe) <em>après</em> avoir exécuté exchucutil.ps1. Sinon, Lync Server ne détectera pas la messagerie unifiée dans la topologie.

6.  À l’aide de l’environnement de ligne de commande Exchange Management Shell ou de la console de gestion Exchange, désactivez les appels sortants pour toutes les passerelles IP associées à chaque plan de numérotation, à l’exception d’une seule.
    
    > [!NOTE]  
    > Cette étape est nécessaire pour que les appels sortants, via le serveur exécutant la messagerie unifiée Exchange Server, vers des utilisateurs externes (comme c’est par exemple le cas pour les scénarios d’émission au téléphone), traversent de manière fiable le pare-feu de l’entreprise.    

    > [!IMPORTANT]  
    > Lors de la sélection de la passerelle IP de messagerie unifiée, qui permet d’autoriser les appels sortants, choisissez celle qui est capable de gérer le plus grand volume de trafic. Ne sélectionnez pas une passerelle IP qui se connecte à un pool directeur Lync Server. Évitez également les pools d’un autre site central ou site de succursale. Vous pouvez utiliser l’une des méthodes suivantes pour empêcher les appels sortants de transiter via une passerelle IP :    
      - Si vous utilisez l’environnement de ligne de commande Exchange Management Shell, désactivez chaque passerelle IP en exécutant la commande suivante :
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        Pour Exchange 2007, consultez « Set-UMIPGateway : aide de Microsoft Exchange 2007 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268687\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268687%26clcid=0x40c)
        
        Pour Exchange 2010, consultez « Set-UMIPGateway : aide de Microsoft Exchange 2010 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268688\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268688%26clcid=0x40c).
    
      - Si vous utilisez la console de gestion Exchange, désactivez la case à cocher **Autoriser les appels sortants via cette passerelle IP de messagerie unifiée**.
    
    > [!IMPORTANT]  
    > Si votre plan de numérotation URI SIP de messagerie unifiée est associé à une seule passerelle IP, n’interdisez pas les appels sortants via cette passerelle.

7.  Créez un standard automatique de messagerie unifiée pour chaque plan de numérotation Lync Server.
    
    > [!IMPORTANT]  
    > N’incluez pas d’espaces dans le nom du standard automatique.    
        
    ```
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    
    Pour plus d’informations, consultez :
    
      - Pour Exchange 2007, consultez « New-UMAutoAttendant : aide de Microsoft Exchange 2007 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268689\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268689%26clcid=0x40c).
    
      - Pour Exchange 2010, consultez « New-UMAutoAttendant : aide de Microsoft Exchange 2010 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268690\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268690%26clcid=0x40c).
    
    L’étape suivante doit être effectuée pour chaque utilisateur une fois que vous avez activé les utilisateurs Lync Server pour Voix Entreprise et que vous connaissez leur URI SIP.

8.  Associez les utilisateurs de la messagerie unifiée Exchange (chacun d’eux devant être configuré avec une boîte aux lettres Exchange) au plan de numérotation de messagerie unifiée et créez un URI SIP pour chaque utilisateur.
    
    > [!NOTE]  
    > Dans l’exemple suivant, <strong>SIPResourceIdentifier</strong> doit être l’adresse SIP de l’utilisateur Lync Server.    
        
    ```
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    
    Pour plus d’informations, consultez :
    
      - Pour Exchange 2007, consultez « Enable-UMMailbox : aide de Microsoft Exchange 2007 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268691\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268691%26clcid=0x40c).
    
      - Pour Exchange 2010, consultez « Enable-UMMailbox : aide de Microsoft Exchange 2010 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268692\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268692%26clcid=0x40c).

