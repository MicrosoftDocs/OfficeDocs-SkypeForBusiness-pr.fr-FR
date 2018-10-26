---
title: "Conf. un itinéraire des communications vocales E9-1-1 dans Lync Server 2013"
TOCtitle: "Conf. un itinéraire des communications vocales E9-1-1 dans Lync Server 2013"
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398496(v=OCS.15)
ms:contentKeyID: 49297490
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer un itinéraire des communications vocales E9-1-1 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-17_

Pour déployer E9-1-1, vous devez d’abord configurer un itinéraire des communications vocales pour les appels d’urgence. Pour plus d’informations sur la création d’itinéraires des communications vocales, voir [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md). Vous pouvez définir plusieurs itinéraires si, par exemple, votre déploiement comporte une jonction SIP principale et une jonction SIP secondaire.

> [!NOTE]  
> Pour inclure les informations d’emplacement dans une E9-1-1 INVITE, vous devez configurer la jonction SIP qui établit la connexion avec le fournisseur de services E9-1-1 pour acheminer les appels d’urgence par l’intermédiaire de la passerelle. Pour ce faire, affectez à l’indicateur EnablePIDFLOSupport de l’applet de commande <strong>Set-CsTrunkConfiguration</strong> la valeur True. La valeur par défaut de EnablePIDFLOSupport est False. Par exemple : <code>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</code><br />
Il n’est pas nécessaire d’activer la réception des emplacements pour les passerelles PSTN (réseau téléphonique commuté) et les passerelles ELIN (Emergency Location Identification Number).

Pour plus d’informations sur l’utilisation des itinéraires des communications vocales, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **New-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

## Pour configurer un itinéraire des communications vocales E9-1-1

1.  Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administration CsVoiceAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez l’applet de commande suivante pour créer un nouvel enregistrement d’utilisation PSTN.
    
    Ce nom doit être identique à celui que vous utiliserez pour le paramètre **PSTN** de la stratégie d’emplacement. Si votre déploiement comporte plusieurs enregistrements d’utilisation téléphonique, l’exemple suivant ajoute « Emergency Usage » (Utilisation d’urgence) à la liste actuelle des utilisations PSTN disponibles. Pour plus d’informations, voir [Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  Exécutez l’applet de commande suivante pour créer un itinéraire des communications vocales à l’aide de l’enregistrement d’utilisation PSTN créé à l’étape précédente.
    
    Le modèle de numéro doit être identique à celui utilisé dans le paramètre **Chaîne de numérotation d’urgence** de la stratégie d’emplacement. Un signe « + » est requis, car Lync ajoute « + » aux appels d’urgence. « Co1-pstngateway-1 » est l’ID du service de jonction SIP pour le fournisseur de services E9-1-1 ou l’ID du service de passerelle ELIN. L’exemple suivant utilise « EmergencyRoute » comme nom de l’itinéraire des communications vocales.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  Éventuellement, pour les connexions à une jonction SIP, nous vous conseillons d’exécuter l’applet de commande suivante pour créer un itinéraire local pour les appels qui ne sont pas gérés par la jonction SIP du fournisseur de services E9-1-1. Cet itinéraire est utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible.
    
    L’exemple suivant part du principe que l’utilisateur a une utilisation « locale » dans sa stratégie de voix.
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

