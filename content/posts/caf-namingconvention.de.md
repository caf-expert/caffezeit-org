---
title: "CAF Namenskonvention"
date: 2022-07-18T13:07:02+02:00
draft: false
tags: ['CAFfe-Zeit', 'Namingconvention', 'Lernen', 'L300']
author: 'Niels Ophey'
cover:
    image: "images/posts/AzureNamingToolv2.png"
    alt: "Azure Naming Tool"
    relative: false
    hidden: false
---

## Namenskonvention

Es ist immer eine große Diskussion, wie eine Namenskonvention für die bereitzustellenden Azure-Ressourcen implementiert werden kann. Oft wird dieser [Artikel](https://docs.microsoft.com/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming) aus dem Microsoft Cloud Adoption Framework for Azure als Ausgangspunkt für die eigene Implementierung in einem Unternehmen verwendet.

Dieses Diagramm zeigt die Komponenten eines Azure-Ressourcennamens:

{{< figure src="../images/resource-naming.png" alt="Components Azure resource name" caption="Components Azure resource name" >}}

## Nächster Schritt 

Was aber, wenn Sie die Namenskonvention Ihrer Umgebung in großem Maßstab und während der Bereitstellung mit Pipelines verwalten möchten? Es gibt ein hilfreiches Tool, das Sie in Betracht ziehen sollten - das **Azure Naming Tool**!

Das Azure Naming Tool wurde unter Verwendung eines Benennungsmusters entwickelt, das auf [Microsoft's best practices](https://docs.microsoft.com/azure/cloud-adoption-framework/ready/azure-best-practices/naming-and-tagging) basiert. Nachdem die Organisationskomponenten von einem Administrator definiert wurden, können Benutzer das Tool verwenden, um einen Namen für die gewünschte Azure-Ressource zu generieren.

Das Interessanteste daran ist, dass Sie dieses Tool als API bereitstellen können, die aus Ihrer Automatisierung heraus verwendet werden kann.

## Screenshot des Azure Naming Tool v2

{{< figure src="../images/AzureNamingToolv2.png" alt="Azure Naming Tool v2" caption="Azure Naming Tool v2" >}}
