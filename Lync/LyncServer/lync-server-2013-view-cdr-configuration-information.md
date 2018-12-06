---
title: "Aff. des info. de configuration de l’enregistrement des détails des appels"
TOCtitle: "Aff. des info. de configuration de l’enregistrement des détails des appels"
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49891397
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations de configuration de l’enregistrement des détails des appels

 

_**Dernière rubrique modifiée :** 2013-02-23_

L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale et unique de paramètres de configuration d’enregistrement des détails des appels est automatiquement créée. Les administrateurs ont également la possibilité de créer des collections de paramètres personnalisées applicables à des sites individuels. Vous pouvez consulter les paramètres de configuration d’enregistrement des détails des appels en cours d’utilisation au sein de votre organisation à l’aide du Panneau de configuration Lync Server ou de l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration).

## Pour afficher les informations de configuration d’enregistrement des détails des appels à l’aide du Panneau de configuration Lync Server

1.  Dans le Panneau de configuration Lync Server, cliquez sur **Surveillance et archivage**.

2.  La liste de tous vos paramètres de configuration d’enregistrement des détails des appels s’affiche sous l’onglet **Enregistrement des détails des appels** ; pour chaque collection de paramètres apparaissent la collection **Nom**, l’indication stipulant si l’enregistrement des détails des appels a été activé ou non (propriété **Enregistrement des détails des appels**) et l’indication stipulant si le vidage a été activé (propriété **Vidage de l’enregistrement des détails des appels**). Pour plus d’informations sur une collection, double-cliquez dessus ou sélectionnez la collection appropriée, cliquez sur **Modifier**, puis sur **Afficher les détails**. Notez que vous pouvez uniquement afficher des informations détaillées pour une seule collection de paramètres de configuration d’enregistrement des détails des appels à la fois.

## Pour afficher les informations de configuration d’enregistrement des détails des appels à l’aide des applets de commande Lync Server Management Shell

Vous pouvez également consulter les paramètres de configuration d’enregistrement des détails des appels à l’aide de Lync Server Management Shell et de l’applet de commande Get-CsCdrConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les informations de configuration d’enregistrement des détails des appels

  - Pour afficher des informations sur tous vos paramètres de configuration d’enregistrement des détails des appels, tapez la commande suivante dans Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsCdrConfiguration
    
    Les informations retournées se présentent ainsi :
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration).

